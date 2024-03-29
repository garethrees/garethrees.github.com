---
layout: post
title: Deploy Any Branch With Capistrano
meta: Deploy any branch to a server with Capistrano.
---

# {{ page.title }}

Originally published on the [Box UK blog](http://www.boxuk.com/blog/deploy-any-branch-with-capistrano).

---

If you [release often](http://www.boxuk.com/blog/towards-faster-releases), you may find you want to push a feature branch on to a server before you merge it in to your master branch.

Capistrano can be set up to deploy a branch and make it the current live branch pretty easily. In this post I’ll show you how to do this.

The most common use case for this is to deploy a new feature to a staging or UAT server before it gets released to all users or meets client approval. For this I’ll assume you have the [Capistrano Multistage extension](https://github.com/capistrano/capistrano/wiki/2.x-Multistage-Extension) installed with at least one staging environment set up, but we’ll come to stages later.

## Configuration

The `-S` switch allows you to specify settings when running cap, and we’ll use this in addition to the usual commands to create the deployment directories.


```sh
$ cap -S branch=my_feature deploy:setup
$ cap -S branch=my_feature deploy
```

To allow Capistrano to get the branch specified you must first set the `:branch` setting. The `fetch` method will return the branch passed using the `-S` switch if it exists, or default to `master` if none was specified.

Create a `:deploy_root` setting with the path to your top-level deployment directory. We use the application name (via the default `:application` setting), and then deploy each branch in to a separate directory underneath it by setting then standard `:deploy_to` setting.

Set the `:shared_path` inside the `:deploy_root` so that all branches can use the shared resources.

```ruby
# config/deploy.rb
set :branch,      fetch(:branch, 'master')
set :deploy_root, "/opt/BoxUK/www/#{ application }"
set :deploy_to,   "#{ deploy_root }/#{ branch }"
set :shared_path, "#{ deploy_root }/#{ shared }"
```

Your tree will look something like this at this point:

```
├── my_application
│   ├── feature_x
│   │   ├── current
│   │   ├── releases
│   ├── feature_y
│   │   ├── current
│   │   ├── releases
│   ├── shared
```

## Custom tasks

We’ll then need to write some custom tasks to handle pointing to the latest release. Create a recipes directory to avoid polluting the main `deploy.rb`.

```sh
$ mkdir config/deploy/recipes
$ touch config/deploy/recipes/deployment.rb
```

Include the custom recipes at the top of `deploy.rb`.

```ruby
# config/deploy.rb
Dir.glob('config/deploy/recipes/*.rb').each { |recipe| load recipe }
```

## Automatically pointing to the current release

Each time a branch is deployed, we’ll have Capistrano point a symlink to the branch. This will reside in in the top level of the `:deploy_root` directory.

```
├── my_application
│   ├── feature_x
│   ├── feature_y
│   ├── live
│   ├── shared
```

Your webserver will need to point at this path. Ours would be:

```
/opt/BoxUK/www/my_application/live
```

Create a task to update where this symlink points to each time the staging server is deployed.

```ruby
# config/deploy/recipes/deployment.rb
namespace :deploy do
  desc 'Link live symlink to latest release'
  task :link_live do
    puts " ** Linking live to latest releasen"
    run "ln -nfs #{ current_path } #{ deploy_root }/live"
 end
end
```

Call the task during the deploy process.

```ruby
# config/deploy.rb
after 'deploy:update', 'deploy:link_live'
```

It must be called after `deploy:update` to ensure `current_path` is pointing at the correct release.

Each time you deploy, the specified branch will automatically become the live version on the staging server.

## Finding the current release

After using this for a few days, we found ourselves asking “What branch is deployed on staging?”. That got annoying pretty fast!

To resolve this, we defined a helper method to capture the currently deployed branch (although if you have a better suggestion for how to parse it out then I’d love to hear it in the comments).


```ruby
# config/deploy/recipes/deployment.rb
def capture_current_branch
  capture("readlink #{ deploy_root }/live").
    gsub(deploy_root, '').
      gsub('current', '').
        gsub('/', '')
end
```

Use this helper in a task to return the live branch and git SHA. I used the utils namespace to avoid cluttering the deploy tasks namespace.

```ruby
# config/deploy/recipes/deployment.rb
namespace :utils do
  desc 'Show deployed revision'
  task :revision, :roles => :app do
    rev    = capture "cat #{ current_path }/REVISION"
    branch = capture_current_branch
    puts "  * REVISION: #{ rev }"    if rev
    puts "  * BRANCH:   #{ branch }" if branch
  end
end
```

Now any member of the team can run cap `utils:revision` to see what’s live.

## What about multistage?

If you’ve followed the steps through, you shouldn’t have to do any more configuration for multistage. Just specify the stage you want to deploy the branch to.

```sh
$ cap uat -S branch=feature_x deploy
$ cap staging -S branch=feature_y deploy
```

## Production

Sometimes you may not want to allow branches to be deployed to the production environment. In these cases simply hard code the branch to master in the production stage configuration.

```ruby
# config/deploy/production.rb
set :branch, 'master'
```

At Box UK we only deploy tags to production. The set method also takes a block, so it’s easy to ask the developer to confirm which tag they want to deploy.

```ruby
# config/deploy/production.rb
set :branch do
  # Warn that branches cannot be deployed
  puts 'Cannot deploy a branch to production' unless fetch(:branch).nil?

    # Get the latest tags and set the default
  default = `git fetch --tags && git tag`.split("n").last

  # Allow the developer to choose a tag to deploy
  tag = Capistrano::CLI.ui.ask "Choose a tag to deploy (make sure to push the tag first): [Default: #{ default }] "

  # Fall back to the default if no tag was specified
  tag = default if tag.empty?

  # Be extra cautious and exit if a tag cannot be found
  if tag.nil?
    puts "Cannot deploy as no tag was found"
    exit
  end

  # Return the tag to deploy
  tag
end
```

## Important Note

When using the `-S` switch be sure to use an uppercase `S`. `cap -h` tells us why.

The variable must be set before the recipes are loaded to avoid the `:branch` setting falling back on the specified default. It’s caught me out a few times!
