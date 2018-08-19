---
layout: post
title: Ruby p vs puts vs print
---

# {{ page.title }}

Ruby has three useful methods for printing information to the command line:
[`Kernel#p`](http://ruby-doc.org/core-2.0/Kernel.html#method-i-p), [`Kernel#print`](http://ruby-doc.org/core-2.0/Kernel.html#method-i-print) and [`Kernel#puts`](http://ruby-doc.org/core-2.0/Kernel.html#method-i-puts).

Fire up `irb` and follow along!

```ruby
> class P
>   def inspect(); "P#inspect"; end
>   def to_s(); "P#to_s"; end
> end

> q = P.new
```

## print

`Kernel#print` is the simplest of printing methods. `print` calls `to_s` on the
object and spits it out to `$stdout`.

```ruby
> print q
P#to_s => nil
```

`print` does not append a new line.

```ruby
> print 1,2,3
123 => nil
```

New lines must be added manually when using `print`.

```ruby
> print 1,"\n",2,"\n",3,"\n"
1
2
3
 => nil
```

## puts

`Kernel#puts` is probably the most common printing methods known to Rubyists.

`puts` is similar to `print` – calling `to_s` – but adds a newline to the output.

```ruby
> puts q
P#to_s
 => nil

> puts 1,2,3
1
2
3
 => nil
```

## p

`Kernel#p` is less well known than `print` and `puts`.

It is similar to `puts` in that it adds a newline, but rather than calling `to_s`, `p` calls `inspect`.

```ruby
> p q
P#inspect
 => P#inspect

> p 1,2,3
1
2
3
=> [1, 2, 3]
```

`p` can be more useful for debugging. As `puts` calls `to_s`, you can't be exactly sure of what class an object is.

```ruby
> puts 1
1
=> nil
> puts '1'
1
=> nil
```

With `p` we get a better indicator of what we're actually looking at.

```ruby
> p 1
1
=> 1
> p '1'
"1"
=> "1"
```

## References

1. <http://www.ruby-doc.org/core-2.0/Kernel.html>
1. <http://mattberther.com/2009/02/11/puts-vs-print-in-ruby>
1. <http://code.activestate.com/lists/ruby-talk/2092/>
1. <http://stackoverflow.com/questions/1255324/p-vs-puts-in-ruby>
