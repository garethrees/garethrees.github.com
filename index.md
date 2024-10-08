---
layout: default
title: Home
---

I currently work at [mySociety](http://www.mysociety.org) leading our [Transparency programme](https://www.mysociety.org/transparency) focused around building [Freedom of Information tools](https://www.whatdotheyknow.com/) installed in over [25 countries](http://alaveteli.org/deployments/).

<p>In 2020-2021 I participated in the <a href="/building-beauty">Building Beauty Online course</a> and the <a href="/building-beauty">Beautiful Software seminar</a>.</p>

In 2017 I was a member of the Welsh Assembly's [Digital News and Engagement Taskforce](https://senedd.wales/senedd-now/news/leighton-andrews-to-head-up-digital-news-and-information-taskforce/). The objective of the Taskforce was to explore and [recommend](https://senedd.wales/senedd-now/news/assembly-encouraged-to-look-beyond-conventional-media-to-reach-people-in-wales-digital-taskforce-launches-creating-a-digital-dialogue-report/) the most effective ways to increase levels of public understanding and engagement with audiences currently disengaged with politics and Welsh affairs.

## Blog

<ul>
  {% for post in site.posts limit:3 %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <time datetime="{{ post.date | date_to_xmlschema }}" class="posted-on minor-note">
      {{ post.date | date_to_long_string }}
    </time>
  </li>
  {% endfor %}

  <li><a href="/blog">More &rarr;</a></li>
</ul>

## Community

I founded and run [cardiffrb](http://cardiffrb.com), a monthly meet up for Ruby programmers in Cardiff, UK.

I created [Cardiff Collective](http://web.archive.org/web/20140212012139/http://collective.cardiffstart.com/) as a place for entrepreneurs in Cardiff to connect and share knowledge.

I worked with [Sam Knight](https://www.samknight.co.uk) to open Welsh politics with [Your Senedd](https://web.archive.org/web/20171020022609/http://yoursenedd.wales/).

## Open Source

- [Contributed](http://contributors.rubyonrails.org/contributors/gareth-rees/commits) code and documentation to [Ruby on Rails](http://rubyonrails.org)
- Fixed a [quote-handling regression in mail](https://github.com/mikel/mail/pull/1023) gem.
- [Several contributions](https://github.com/ddollar/github-backup/commits?author=garethrees) to github-backup including [updating to GitHub API v3](https://github.com/ddollar/github-backup/pull/8)
- [Forked acl_system2](https://github.com/boxuk/acl_system2) to [add Rails 3 compatibility](https://github.com/boxuk/acl_system2/pull/5) and release as a [rubygem](https://rubygems.org/gems/acl_system2)
- [Fixed bug](https://github.com/heapsource/active_model_otp/pull/27) in `ActiveModel::Otp` while using ActiveRecord
- [Added a default option](https://github.com/thoughtbot/paperclip/pull/1061) to Thoughtbot's [paperclip](https://github.com/thoughtbot/paperclip) gem
- [Contributor](https://github.com/thoughtbot/trail-map/graphs/contributors) to Thoughtbot's [Trail Map](https://github.com/thoughtbot/trail-map)
- [Reformatted](https://github.com/thoughtbot/fistface/pull/2) Thoughtbot's [Fist Face](https://github.com/thoughtbot/fistface) gem to use Sinatra's modular extension style
- [Touched up](https://github.com/ryanb/railscasts/pull/10) the watch button on [Railscasts](http://railscasts.com) <span class="minor-note">(First Pull Request)</span>
- [More &rarr;](https://github.com/garethrees?tab=contributions&period=monthly)

### Rubygems

- [**readingtime**](http://rubygems.org/gems/readingtime): Estimates reading time of a Ruby String object
- [**ampersat**](http://rubygems.org/gems/ampersat): Calculates which email domains your subscribers use
- [**hunter**](http://rubygems.org/gems/hunter): Calculates which email domains your subscribers use
- [**twalk**](http://rubygems.org/gems/twalk): Twalk displays tweets of your followers who are talking to one another
- [**ncbi_blast_results_parser**](https://rubygems.org/gems/ncbi_blast_results_parser): Parses HTML 'API' responses from [NCBI Blast](http://blast.ncbi.nlm.nih.gov/Blast.cgi)
- [More &rarr;](http://rubygems.org/profiles/garethrees)

### Other

- [**Git to SVN Guide**](https://github.com/garethrees/git-to-svn-guide): A guide of how to use SVN when you're familiar with [Git](http://git-scm.org)
- [**Example.html**](http://github.com/garethrees/example.html): A file full of standard HTML5 elements to check your stylesheet doesn’t miss anything out _([Demo](http://garethrees.github.com/example.html))_
- [**Vanilla CSS**](http://github.com/garethrees/vanillacss): An empty stylesheet containing all the standard HTML tags to build up your default styles after applying a reset
- [**Anchors**](http://github.com/garethrees/anchors): A collection of link styles and some clever things you can do with the HTML anchor tag _([Demo](http://garethrees.github.com/anchors))_

