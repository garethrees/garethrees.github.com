---
layout: post
title: Deploy any branch with Capistrano
meta: Deploy a branch to a staging server with Capistrano before you merge to master to get feedback or sign off.
---

# {{ page.title }}

Many of you may have an internal or staging server where you test out new branches of code before they go fully in to production.

If you [release often](http://www.boxuk.com/blog/towards-faster-releases), you may find you want to push the feature branch you're working on to the staging server before you merge to master to get some feedback or sign off.

[Capistrano](https://github.com/capistrano/capistrano) makes this pretty easy.

I'll assume you have the [Capistrano Multistage extension](https://github.com/capistrano/capistrano/wiki/2.x-Multistage-Extension) set up with at least one staging environment.

## Configuring the stage

The `-S` switch allows you to specify the branch to deploy when running `cap`:

```sh
$ cap staging -S branch=my_feature deploy:setup
$ cap staging -S branch=my_feature deploy
```

To allow Capistrano to get the specified branch you must set the `:branch` setting in the stage's environment file. The `fetch` method will return the branch passed using the `-S` switch if it exists, or default to `master` if none was specified.

Create a `:deploy_root` setting with the path to your top-level deployment directory. We use the application name, and then deploy each branch in to a separate directory underneath it by setting the standard `:deploy_to` setting.

```ruby
# config/deploy/staging.rb

set :branch,       fetch(:branch, 'master')
set :deploy_root,  "/opt/BoxUK/www/#{ CONFIG['staging']['application_name'] }"
set :deploy_to,    "#{ deploy_root }/#{ branch }"
```

Your tree will look something like this at this point:

```sh
├── my_application
│   ├── feature_x
│   └── test_feature
```

## Custom tasks

We'll need to write some custom tasks for the next step. Create `/config/deploy/custom/staging_tasks.rb` and load the custom tasks at the top of `deploy.rb`

```ruby
# config/deploy.rb

# Load custom recipies
Dir.glob('config/deploy/custom/*.rb').each { |recipe| load recipe }
```
## Automatically pointing to the current release

By now you should be able to deploy any branch to your staging server. Next we'll configure the deployment script to point a symlink at the last branch deployed.

You'll want to point your webserver to the path you set `:deploy_root` to be, plus `/live`. Ours would be:

```
/opt/BoxUK/www/my_application/live
```

Create a task to update where this symlink points each time the staging server is deployed to.

```ruby
# config/deploy/custom/staging_tasks.rb

namespace :deploy do

  desc 'Link live symlink to latest release'
  task :link_live do
    if stage.to_s == 'staging'
      puts " ** Linking live to latest release\n"
      run "ln -nfs #{ current_path } #{ deploy_root }/live"
    end
  end

end
```

Now you'll need to call this task during the deploy process.

```ruby
# config/deploy.rb

after 'deploy:update', 'deploy:link_live'
```

It must be called after `deploy:update` to ensure `current_path` is pointing at the correct release.

Now each time you deploy, the specified branch will automatically become the live version on the staging server.

## Finding out the current release

After using this for a few days, we found ourselves asking _"What branch is deployed on staging?"_. That got annoying pretty fast!

First you can define a helper method to capture the currently deployed branch. If you have a better suggestion for how to parse it out then I'd love to hear it in the comments.

```ruby
# config/deploy/custom/staging_tasks.rb

def capture_current_branch
  capture("readlink #{ deploy_root }/live").
    gsub(deploy_root, '').
      gsub('current', '').
        gsub('/', '')
end
```

You can then use this helper to add a task to return the live branch and git SHA. I used the `utils` namespace to avoid cluttering the `deploy` tasks namespace.

```ruby
# config/deploy/custom/staging_tasks.rb

desc 'Show deployed revision'
task :revision, :roles => :app do
  rev    = capture "cat #{ current_path }/REVISION"
  branch = capture_current_branch

  puts " ** REVISION: #{ rev }"    if rev
  puts "  * BRANCH:   #{ branch }" if branch
end
```

Now any member of the team can run `cap staging utils:revision` to see what's live on the staging server.

