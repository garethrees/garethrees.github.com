---
layout: post
title: self in Ruby
meta: Some examples of what self is in different contexts
---

# `self` in Ruby

```ruby
module M

  def y
    self # => whatever includes M
  end

end

class C
  include M

  self # => C

  def self.x
    self # => C
  end

  def x
    self # => instance of C
  end

end

class D < C ; end

>> self
=> main

>> C.x
=> C

>> c = C.new
=> #<C:0x007fbec260cba0>
>> c.x
=> #<C:0x007fbec260cba0>
>> c.y
=> #<C:0x007fbec260cba0>

>> D.x
=> D
```
