---
layout: post
title: "Elegant Objects: Composable Decorators"
---

# {{ page.title }}

There's an interesting section in [Elegant Objects Volume 1](https://www.yegor256.com/elegant-objects.html) on "Composable Decorators".

The example, as written, is:

```java
names = new Sorted(
  new Unique(
    new Capitalized(
      new Replaced(
        new FileNames(
          new Directory(
            "/var/users/*.xml"
          )
        ),
        "([^.]+)\\.xml",
        "$1"
      )
    )
  )
);
```

So, assuming my filesystem was case-sensitive and I had the following files:

```
gareth: /var/users
$ tree
.
├── alice.xml
├── ALICE.XML
└── bob.xml
```

The code above would set `names` as a new `Sorted` instance with elements `"Alice"` and `"Bob"`; something like:

```ruby
names.to_a
# => ["Alice", "Bob"]
```

[Yegor](https://www.yegor256.com) praises the code for being clean and purely declarative. I quite like the style, but in Ruby at least, it looks like a lot more effort to write than chaining a few methods.

```ruby
Dir.glob("/var/users/*.xml").
  map { |f| File.basename(f, '.xml').capitalize }.
  uniq.
  sort
# => ["Alice", "Bob"]
```

Here's a full Ruby implementation of the snippet in the book:

```ruby
class Directory
  include Enumerable

  def initialize(glob)
    @glob = glob
  end

  def each
    Dir.glob(@glob).each { |path| yield path }
  end
end

class FileNames
  include Enumerable

  def initialize(files)
    @files = files
  end

  def each
    @files.each { |file| yield File.basename(file) }
  end
end

# Replaced.new(%w[alice.xml bob.xml], /([^.]+)\.xml/, '\1').to_a
# => ["alice", "bob"]
class Replaced
  include Enumerable

  def initialize(list, regexp, replacement)
    @list = list
    @regexp = regexp
    @replacement = replacement
  end

  def each
    @list.each do |element|
      yield element.to_s.gsub(@regexp, @replacement)
    end
  end
end

# Capitalized.new(%w[x y z]).to_a
# => ["X", "Y", "Z"]
class Capitalized
  include Enumerable

  def initialize(list)
    @list = list
  end

  def each
    @list.each { |element| yield element.to_s.capitalize }
  end
end

# Unique.new([8,8,2,2]).to_a
# => [8, 2]
class Unique
  include Enumerable

  def initialize(list)
    @list = list
  end

  def each
    @list.uniq.each { |element| yield element }
  end
end

# Sorted.new([8,5,2,7]).to_a
# => [2, 5, 7, 8]
class Sorted
  include Enumerable

  def initialize(list)
    @list = list
  end

  def each
    @list.sort.each { |element| yield element }
  end
end

names = Sorted.new(
  Unique.new(
    Capitalized.new(
      Replaced.new(
        FileNames.new(
          Directory.new('/var/users/*.xml')
        ),
        /([^.]+)\.xml/,
        '\1'
      )
    )
  )
)

names.to_a
# => ["Alice", "Bob"]
```

That's a lot of code! Even at the call-site, there's just _more_ that needs to be written.

```ruby
def user_names
  Dir.glob("/var/users/*.xml").
    map { |f| File.basename(f, '.xml').capitalize }.
    uniq.
    sort
end

# vs…

def user_names
  Sorted.new(
    Unique.new(
      Capitalized.new(
        Replaced.new(
          FileNames.new(
            Directory.new('/var/users/*.xml')
          ),
          /([^.]+)\.xml/,
          '\1'
        )
      )
    )
  )
end
```

Where this approach shines, though, is where each of these classes make up part of a library.

Its a little hard to see in this example, as the decorators re-implement standard Ruby methods. However, if this was all largely custom domain logic, it would be incredibly hard to re-compose the chained approach.

There'd be a lot of re-implementation, changing or making new methods that return the values you need. With the composable decorators, it would be much easier to pick and choose from the classes you need – or add additional classes – to construct the new method.

There's more about this chapter of the book at [OOP Alternative to Utility Classes](https://www.yegor256.com/2014/05/05/oop-alternative-to-utility-classes.html).
