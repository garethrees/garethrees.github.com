---
layout: post
title: Private attr methods in Ruby
---

# {{ page.title }}

You're probably well aware that you can use the `attr_` family of methods to create getters and setters for class attributes. You may not know that you can actually make these private without having to write your own.

Here's a simple class with one attribute to demonstrate.

```ruby
class Post

  def initialize
    @title = 'Default'
  end

  attr_reader :title

  def rename!
    self.title = 'Renamed!'
  end

  private

  attr_writer :title

end
```

Here, the API allows `@title` to be read via the `title` instance method, created by `attr_reader :title`.

```ruby
>> p.title
=> "Default"
```

However, `@title` may _not_ be written to by the user of the `Post` class.

```ruby
>> p.title = 'A New Title'
NoMethodError: private method `title=' called for #<Post:0x007fa8e8c3a378 @title="Default">
	from (irb):20
	from /Users/gareth/.rvm/rubies/ruby-1.9.3-p327/bin/irb:16:in `<main>'
```

You can still use `#title=` inside the `Post` class as you'd expect though.

```ruby
>> p.rename!
=> "Renamed!"
>> p.title
=> "Renamed!"
```
