---
layout: post
title: Regex Match Groups in Ruby
---

# {{ page.title }}

You can use Ruby to create hash-like objects from a regex match. Lets say we
wanted to match a [Jekyll](http://jekyllrb.com) post title such as
`2013-06-23-regex-match-groups-in-ruby.md`.

First we must define the regex to use.

{% highlight ruby %}
PATTERN = /\A(?<year>\d{4})-(?<month>\d{2})-(?<day>\d{2})-(?<basename>([a-zA-Z]|-)*).(?<extension>.*)\z/
{% endhighlight %}

It looks a little complicated, but its not too bad when you break it down.

    \A                          # Start of the String
    (?<year>\d{4})              # Group named 'year' matching 4 digits
    (?<month>\d{2})             # Group named 'month' matching 2 digits
    (?<day>\d{2})               # Group named 'day' matching 2 digits
    (?<basename>([a-zA-Z]|-)*)  # Group named 'basename' matching letters
                                # or hyphens
    (?<extension>.*)            # Group named 'extension' matching anything
    \z                          # End of the String
    
The pattern can now be used against a `String` to find a match.

{% highlight ruby %}
post   = '2013-06-23-regex-match-groups-in-ruby.md'
result = post.match(PATTERN)
{% endhighlight %}

Now, the interesting bit.

What's really nice is that `String#match` returns a `MatchData` object, which
can be treated like a `Hash` with each match group's results accessible by a key
with the name of the group.

{% highlight ruby %}
>> result
=> #<MatchData "2013-06-23-regex-match-groups-in-ruby.md" year:"2013" month:"06" day:"23" basename:"regex-match-groups-in-ruby" extension:"md">

>> result[:year]
=> "2013"

>> result[:month]
=> "06"

>> result[:day]
=> "23"

>> result[:basename]
=> "regex-match-groups-in-ruby"

>> result[:extension]
=> "md"
{% endhighlight %}

This could be used to create a friendly class to represent the post.

{% highlight ruby %}
class Post

  PATTERN = /\A(?<year>\d{4})-(?<month>\d{2})-(?<day>\d{2})-(?<basename>([a-zA-Z]|-)*).(?<extension>.*)\z/

  attr_accessor :year, :month, :day, :title, :format

  def initialize(path, pattern=PATTERN)
    attrs          = path.match(pattern)
    self.year      = attrs[:year].to_i
    self.month     = attrs[:month].to_i
    self.day       = attrs[:day].to_i
    self.title     = attrs[:basename].split('-').each(&:capitalize!).join(' ')
    self.format    = attrs[:extension].to_sym
  end

end
{% endhighlight %}

You might then use the `Post` class by globbing a directory to collect all the
posts.

{% highlight ruby %}
>> posts = Dir.glob('./_posts/*.md').collect { |p| Post.new(File.basename(p)) }
>> posts.first.title
=> "First Post"
{% endhighlight %}
