---
layout: post
title: Use Parentheses With defined? Keyword in Ruby
---

# {{ page.title }}

Ruby's [`defined?`](http://ruby-doc.org/docs/keywords/1.9/Object.html#method-i-defined-3F) keyword has a bit of a gotcha that's easy to get wrong.

## What is `defined?`

> `defined?` expression tests whether or not expression refers to anything
> recognizable (literal object, local variable that has been initialized,
> method name visible from the current scope, etc.). The return value is nil if
> the expression cannot be resolved. Otherwise, the return value provides
> information about the expression.
>
> Note that the expression is not executed.

So a few examples…

When `x` isn't defined we'll get `nil`.

```ruby
defined? x
=> nil
```

When `x` is a variable, it will return `"local-variable"`.

```ruby
x = 1
defined? x
=> "local-variable"
```

`defined?` can also test expressions.

```ruby
defined? x + 1 && x + 2
=> "expression"
```

 Remember, the expression is not executed

```ruby
defined? x + 1 && x + 2
=> "expression"
x
=> 1
```

## Use Parentheses

In a Rails partial template you might want to check that a local variable has
been passed to the partial before you try to do something with it. `defined?` is
the de-facto way of doing this.

You might also want to check the value of the variable if it does exist:

```erb
<% if defined? follower_count && follower_count > 0 %>
  <!-- Do A -->
<% else %>
  <!-- Do B -->
<% end %>
```

In this case `defined?` treats `follower_count && follower_count > 0` as the
expression to test, and since it can execute it, the return value is
`"expression"` – not the return value of the expression. In this case, `A` will
always happen, regardless of whether `follower_count` is `0` or not.

To avoid this issue, ensure the variable (or expression) you're testing is
wrapped in parentheses.

```erb
<% if defined?(follower_count) && follower_count > 0 %>
  <!-- Do A -->
<% else %>
  <!-- Do B -->
<% end %>
```
