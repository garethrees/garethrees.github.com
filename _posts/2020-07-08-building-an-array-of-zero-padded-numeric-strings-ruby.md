---
layout: post
title: Building an array of zero-padded numeric strings in Ruby
---

# {{ page.title }}

I wanted to create a handful of test files with filenames that were zero-padded.

There's a clunky, imperative way to do this…

```ruby
files = []

4.times do |i|
  next if i.zero?
  id = format('%06d', i)
  files << "file-#{ id }.md"
end

files
# => ["file-000001.md", "file-000002.md", "file-000003.md"]
```

…or a much nicer functional-style:

```ruby
2.times.
  reduce(['000001']) { |memo| memo << memo.last.next }.
  map { |id| "file-#{ id }.md" }
# => ["file-000001.md", "file-000002.md", "file-000003.md"]
```

Or even shorter, if you don't mind mutating a variable…

```ruby
start = '000000'
3.times.reduce([]) { |memo| memo << "file-#{ start.next! }.md" }
# => ["file-000001.md", "file-000002.md", "file-000003.md"]
```
