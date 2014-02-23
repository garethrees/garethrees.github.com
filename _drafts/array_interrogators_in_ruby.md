---
layout: post
title: Array Interrogators in Ruby
---

Array Interrogators in Ruby
===========================

Interrogators are methods that end with a question mark (`?`) in Ruby.

When I was a beginner I could never remember where some of the methods available to `Array` came from.

The main places you might find interrogators are in the `Array` class itself or included by the `Enumerable` module. [Rails](https://github.com/rails/rails/blob/master/activesupport/lib/active_support/core_ext/) also monkey-patches some additional methods.

Lets start with the basics.

Array
-----

**[`empty?`](http://ruby-doc.org/core-2.1.0/Array.html#method-i-empty-3F)**

Returns `true` if the array contains no elements.

Even if it contains a single element of `nil`, the array is not empty.

{% highlight ruby %}
[].empty?      #=> true
[1].empty?     #=> false
[1, 2].empty?  #=> false
[nil].empty?   #=> false
{% endhighlight %}

**[`include?`](http://ruby-doc.org/core-2.1.0/Array.html#method-i-include-3F)**

Returns `true` if the given object is present in the array.

{% highlight ruby %}
['a', 'b'].include?('a')  #=> true
['a', 'b'].include?('c')  #=> false
{% endhighlight %}

Enumerable
----------

[`Enumerable`](http://ruby-doc.org/core-2.1.0/Enumerable.html) is included in to `Array` by default to enhance its capabilities.

> The Enumerable mixin provides collection classes with several traversal and searching methods, and with the ability to sort.

**[`all?`](http://ruby-doc.org/core-2.1.0/Enumerable.html#method-i-all-3F)**

Checks each element against the specified criteria. Returns `true` as long as the block never returns `false` or `nil`.

{% highlight ruby %}
%w[ant bear cat].all? { |word| word.length >= 3 }  #=> true
%w[ant bear cat].all? { |word| word.length >= 4 }  #=> false
{% endhighlight %}

If the block is not given, Ruby adds an implicit block which will cause `all?` to return `true` when none of the collection members are `false` or `nil`.

{% highlight ruby %}
[nil, true, 99].all?  #=> false
{% endhighlight %}

**[`any?`](http://ruby-doc.org/core-2.1.0/Enumerable.html#method-i-any-3F)**

Much like `.all?`, but `any?` returns `true` if the block returns something other than `false` or `nil` one or more times.

{% highlight ruby %}
%w[ant bear cat].any? { |word| word.length >= 3 }  #=> true
%w[ant bear cat].any? { |word| word.length >= 4 }  #=> true
[nil, true, 99].any?                               #=> true
{% endhighlight %}

**RAILS**

**[`none?`](http://ruby-doc.org/core-2.1.0/Enumerable.html#method-i-none-3F)**

A bit like the reverse of `.all?`. Passes each element of the collection to the given block. The method returns `true` if the block never returns `true` for all elements

{% highlight ruby %}
%w[ant bear cat].none? { |word| word.length == 5 }  #=> true
%w[ant bear cat].none? { |word| word.length >= 4 }  #=> false
{% endhighlight %}

If the block is not given, `none?` will return `true` only if none of the collection members is `true`.

{% highlight ruby %}
[].none?            #=> true
[nil].none?         #=> true
[nil, false].none?  #=> true
{% endhighlight %}

**[`one?`](http://ruby-doc.org/core-2.1.0/Enumerable.html#method-i-one-3F)**

A bit like the reverse of `.any?`. Passes each element of the collection to the given block. The method returns `true` if the block returns `true` exactly once.

{% highlight ruby %}
%w[ant bear cat].one? { |word| word.length == 4 }  #=> true
%w[ant bear cat].one? { |word| word.length > 4 }   #=> false
%w[ant bear cat].one? { |word| word.length < 4 }   #=> false
{% endhighlight %}

If the block is not given, one? will return true only if exactly one of the collection members is true.

{% highlight ruby %}
[ nil, true, 99 ].one?     #=> false
[ nil, true, false ].one?  #=> true
{% endhighlight %}

Rails
-----

[Rails](https://github.com/rails/rails/blob/master/activesupport/lib/active_support/core_ext/) monkey-patches some of Ruby's core library to enhance the functionality within the Rails environment. Rails doesn't add any interrogators to `Array`, but it does add some to `Object` and `Enumerable`.

**[`blank?`](http://api.rubyonrails.org/classes/Object.html#method-i-blank-3F)**

> An object is blank if it's `false`, `empty`, or a whitespace string. For example, `''`, `' '`, `nil`, `[]`, and `{}` are all blank.

In the case of `Array`, this acts in the same way as `Array#empty?`.

{% highlight ruby %}
[].blank?      #=> true
[1].blank?     #=> false
[1, 2].blank?  #=> false
[nil].blank?   #=> false
{% endhighlight %}

**[`many?`](http://api.rubyonrails.org/classes/Enumerable.html#method-i-many-3F)**

Returns `true` if the enumerable has more than 1 element. This is functionally equivalent to `array.size > 1`.

{% highlight ruby %}
[1].many?     #=> false
[1, 2].many?  #=> true
{% endhighlight %}

`many?` can also be given a block, and returns `true` if more than one element returns something other than `nil` or `false` when compared.

{% highlight ruby %}
%w[ant cat hello].many? { |word| word.length > 3 }    #=> false 
%w[ant hello world].many? { |word| word.length > 3 }  #=> true 
{% endhighlight %}

**[`present?`](http://api.rubyonrails.org/classes/Object.html#method-i-present-3F)**

An object is present if it's not `blank?`. This is exactly the same as `!array.blank?`.

{% highlight ruby %}
[].present?      #=> false
[1].present?     #=> true
[1, 2].present?  #=> true
[nil].present?   #=> true
{% endhighlight %}



CollectionProxy
===============

.any? http://api.rubyonrails.org/classes/ActiveRecord/Associations/CollectionProxy.html#method-i-any-3F


.empty? http://api.rubyonrails.org/classes/ActiveRecord/Associations/CollectionProxy.html#method-i-empty-3F

.many? http://api.rubyonrails.org/classes/ActiveRecord/Associations/CollectionProxy.html#method-i-many-3F

Relation
========

.any? http://api.rubyonrails.org/classes/ActiveRecord/Relation.html#method-i-any-3F

.blank?
http://api.rubyonrails.org/classes/ActiveRecord/Relation.html#method-i-blank-3F

.empty? http://api.rubyonrails.org/classes/ActiveRecord/Relation.html#method-i-empty-3F

.many?
http://api.rubyonrails.org/classes/ActiveRecord/Relation.html#method-i-many-3F






rails


.any? (http://api.rubyonrails.org/classes/ActiveRecord/Associations/CollectionProxy.html#method-i-any-3F)

https://github.com/rails/rails/blob/master/activerecord/lib/active_record/associations/collection_proxy.rb