---
layout: post
title: "Why I use protected attr_reader in Ruby"
---

# {{ page.title }}

For a while I've been using a pattern of declaring `protected` `attr_reader`s.

```ruby
class Foo
  def initialize(bar)
    @bar = bar
  end

  protected

  attr_reader :bar
end
```

There are three main reasons for this:

1. [`public` accessors are bad](#why-not-use-public-accessors)
1. [`attr_reader` has better error handling than instance variables](#error-handling-of-methods-is-better)
1. [`protected` makes equality comparison easier](#equality-comparison)

## Why not use `public` accessors?

It's common to see `attr_*` methods defined in the public scope of a class.

[Much](http://wiki.c2.com/?AccessorsAreEvil) [has](https://www.javaworld.com/article/2073723/why-getter-and-setter-methods-are-evil.html) [been](http://wiki.c2.com/?TellDontAsk) [written](https://www.yegor256.com/2014/09/16/getters-and-setters-are-evil.html) about the problems of getters and setters, so I won't go over this in too much detail.

The gist is that an a well designed class is composed of one or more  [encapsulated](https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)) objects.

> Encapsulation is used to hide the values or state of a structured data object inside a class.

A good object should be a black box with a clearly articulated set of behaviours – the public API. When we expose the encapsulated objects to the outside world, we allow the boundaries of our system to blur and become tangled.

Public getters (`attr_reader`) and setters (`attr_writer`) cause different problems.

Public **getters** violate the principle of ["Tell, Don't Ask"](http://wiki.c2.com/?TellDontAsk).

<details markdown="1">
  <summary>
    Allowing users of the object to access its attributes encourages the calling code to get complicated.
  </summary>

```ruby
# BAD
class Post
  attr_reader :title, :status

  def initialize(title:, status:)
    @title = title
    @status = status
  end
end

posts = [
  Post.new(title: 'A draft post', status: 'draft'),
  Post.new(title: 'A published post', status: 'published')
]

# Somewhere where we're listing all posts.
# Here we're reaching into post and operating on its encapsulated members.
posts.each do |post|
  puts "[#{ post.status.upcase }] #{ post.title }"
end
```
</details>

If we remove the `attr_reader`s from public visibility, we're forced to define _behaviour_ on the class.

<details markdown="1">
  <summary>
    If we change our minds about what we want to display when a post is printed, we can just change the implementation details in <code class="highlighter-rouge">Post#print</code>, rather than having to <a href="https://en.wikipedia.org/wiki/Shotgun_surgery">search around the application</a> for places where we’ve asked for all the attributes we need for printing posts.
  </summary>

```ruby
# GOOD
class Post
  def initialize(title:, status:)
    @title = title
    @status = status
  end

  def print
    puts "[#{ status.upcase }] #{ title }"
  end

  private

  attr_reader :title, :status
end

posts = [
  Post.new(title: 'A draft post', status: 'draft'),
  Post.new(title: 'A published post', status: 'published')
]

# Somewhere where we're listing all posts.
# Now we're telling the post to print itself.
posts.each(&:print)
```
</details>

Public **setters**, in my opinion, are even worse. Similar to the problem above, they encourage users of the object to define behaviour outside of the class.

<details markdown="1">
  <summary>
    In this case, we're defining what it means to "publish" a post outside of <code>Post</code>.
  </summary>

```ruby
# BAD
class Post
  attr_reader :title
  attr_accessor :status

  def initialize(title:, status:)
    @title = title
    @status = status
  end
end

posts = Post.new(title: 'A draft post', status: 'draft')

# Somewhere where we're publishing a post.
# This is likely defined in a controller where a user has interacted with the UI
# to publish their post – quite distant from the "Post" class.
post.status = 'published'
```
</details>

Again, we want behaviour relating to the `post` defined _in_ the `Post` class.

<details markdown="1">
  <summary>
    Here we avoid allowing calling code to mutate the <code>post</code> instance directly.
  </summary>

```ruby
# GOOD
class Post
  def initialize(title:, status:)
    @title = title
    @status = status
  end

  def publish
    @status = 'published'
  end

  private

  attr_reader :title, :status
end

posts = Post.new(title: 'A draft post', status: 'draft')

# Somewhere where we're publishing a post.
# Post now controls what it means to publish a post.
post.publish
```
</details>

Public setters have a tendency to cause calling code to become extremely complex as requirements expand.

<details markdown="1">
  <summary>
    Imagine our publishing workflow as we add features.
  </summary>

Now we want to record who and when the post was published.

```ruby
# BAD
# Using public setters encourages lots of complexity in our
# PublishingController.
class PublishingController
  def publish_post(post)
    post.status = 'published'
    post.published_at = Time.now
    post.published_by = editor
  end
end

# GOOD
class Editor
  def publish(post)
    post.publsh(self)
  end
end

class Post
  def publish(published_by)
    @status = 'published'
    @published_at = Time.now
    @published_by = published_by
  end
end

# Now we've defined the behaviour in the relevant objects, we're simply telling 
# the editor to publish the post.
class PublishingController
  def publish_post(post)
    editor.publish(post)
  end
end
```
</details>

## Error handling of methods is better

We could avoid using `attr_reader` altogether and directly call the instance variables.

<details markdown="1">
  <summary>
    Instance variables default to <code>nil</code>, which can be misleading if you make a mistake when typing the instance variable.
  </summary>

```ruby
class Post
  def initialize(title:, status:)
    @title = title
    @status = status
  end

  def published?
    # Oops, typo
    @staaaaaatus == 'published'
  end
end

post = Post.new(title: 'A post', status: 'published')
post.published?
# => false
```
</details>

`attr_reader`s define methods, so making a mistake is much more obvious.

<details markdown="1">
  <summary>
    When you call an undefined method a <code>NameError</code> is raised, making it much easier to figure out that you've made a mistake.
  </summary>

```ruby
class Post
  def initialize(title:, status:)
    @title = title
    @status = status
  end

  def published?
    # Oops, typo
    staaaaaatus == 'published'
  end

  private

  attr_reader :status
end

post = Post.new(title: 'A post', status: 'published')
post.published?
# => NameError (undefined local variable or method `staaaaaatus' for
     #<Post:0x00007fb4248bff58 @title="A post", @status="published">)
```
</details>


## Equality comparison

Up until now I've been using `private` for the examples, but this post is all about why I use `protected`.

One case where you _do_ want access to the attributes of an object are when comparing whether two objects are the same.

```ruby
def ==(other)
  title == other.title &&
    status == other.status
end
```

<details markdown="1">
  <summary>
    If we were to use <code>private</code> we'd get a <code>NoMethodError</code>. when trying to call <code>other.title</code>.
  </summary>

```ruby
class Post
  def initialize(title:, status:)
    @title = title
    @status = status
  end

  def ==(other)
    title == other.title &&
      status == other.status
  end

  private

  attr_reader :title, :status
end

post_1 = Post.new(title: 'A post', status: 'published')
post_2 = Post.new(title: 'A post', status: 'published')

post_1 == post_2
# NoMethodError (private method `title' called for
  #<Post:0x00007fdf0b09f280 @title="A post", @status="published">)
```
</details>

Protected methods are a little different from private methods. In addition to being able to call methods with an implicit receiver, you can call a protected method with an explicit receiver as long as this receiver is `self` _or an object of the same class as `self`_.

<details markdown="1">
  <summary>
      By using <code>protected</code> we keep our encapsulated objects hidden from public tampering, but allow access when we compare instances of the same class.
  </summary>

```ruby
class Post
  def initialize(title:, status:)
    @title = title
    @status = status
  end

  def ==(other)
    title == other.title &&
      status == other.status
  end

  protected

  attr_reader :title, :status
end

post_1 = Post.new(title: 'A post', status: 'published')
post_2 = Post.new(title: 'A post', status: 'published')

post_1 == post_2
# true

post_1.status
# NoMethodError (protected method `status' called for
  #<Post:0x00007fdfb7189428 @title="A post", @status="published">)
```
</details>

This approach has been working well for me 90% of the time. There are a couple of downsides to be aware of though.

According to [rubyguides.com](https://www.rubyguides.com/2018/10/method-visibility/), "A protected method is slow because it can’t use inline cache." In 2018 this resulted in "a difference of 8.5% in performance".

<details markdown="1">
  <summary>
    The other downside is that you can't compare duck-types of different classes in this way, since <code>protected</code> checks class.
  </summary>

```ruby
class Blog
  def initialize(title:, status:)
    @title = title
    @status = status
  end

  protected

  attr_reader :title, :status
end

blog = Blog.new(title: 'A post', status: 'published')
post_1 == blog
# NoMethodError (protected method `title' called for
  #<Post:0x00007fdfb7189428 @title="A post", @status="published">)
```
</details>

It's pretty rare that either of these downsides has caused a problem for me, and any pain has been far outweighed by cleaner code resulting from avoiding public getters and setters.
