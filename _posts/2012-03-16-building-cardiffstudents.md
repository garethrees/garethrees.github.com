---
layout: post
title: Building cardiffstudents.com
meta: An overview of design decisions made when building cardiffstudents.com
---

# {{ page.title }}

[Cardiffstudents](http://cardiffstudents.com) requires a weird mix of simplicity and editability.

Content creators rarely directly modify the website. Instead, content is passed to an editor in charge of updates.

The dynamic content focuses on three main areas:

- What’s happening this minute – _Twitter Feed_
- What’s happening this week – _Blog Posts_
- What’s happening this month – _Slideshow_

Static content focuses on:

- What's always happening and what the organisation stands for – _Pages_

## Latest News

Latest news is handled by [Twitter](http://twitter.com) since its used regularly enough and gives us chance to connect with the audience.

## Blog Posts

A simple blogging engine handles less frequent news and articles, which is where the majority of content is placed. Blogs have a simple title, snapshot and main body format so that there is minimal requirement on the content editor. A feature image can also be added to the article.

![New article structure](/images/posts/new-article-structure.png)

Editors can schedule the article for future release to aid them in managing content updates. They can also tag and attribute a department author to the article if required.

![New article metadata](/images/posts/new-article-metadata.png)

Finally, the editor can choose to publish the article or simply save it for later publishing. Published articles can also be unpublished at the click of a button.

![Save and publish an article](/images/posts/new-article-publish.png)
![Update and unpublish an article](/images/posts/new-article-unpublish.png)

Articles are only given status tags when necessary to remove visual clutter.

![Article tags](/images/posts/article-tags.png)

Interface copy is also tweaked depending on the state. Published articles have minimal hinting whereas scheduled articles emphasise the date at which they will be made available.

![Article publish date](/images/posts/article-publish-date.png)

## Campaign Slideshow

The campaign slideshow is intended to promote up to three longer term campaigns that the Students' Union runs.

![New Campaign Slide](/images/posts/new-campaign-slide.png)

The last three updated campaigns marked `live` are picked to appear on the slideshow. This is to ensure rotation and updates. Recurring campaigns can be hidden for re-use the next time the campaign is run.

![Live Campaign Slides](/images/posts/live-campaign-slides.png)

## Pages

For slower moving content – i.e. content that only gets updated a few times a year – [Thoughtbot's HighVoltage  gem](https://github.com/thoughtbot/high_voltage) was used. To add a page, the developer simply needs to add a new view, stylesheet and javascript file in the appropriate `pages` directory.

![Pages Directory Structure](/images/posts/pages-directory-structure.png)

This format was primarily chosen so that the developer has full control over the markup and styling. The previous iteration of [cardiffstudents](http://cardiffstudents.com) stored full page layouts in the database which lead to a rigid design structure.

To allow non-developers to edit content on these 'static' pages, [Mercury Editor](http://jejacks0n.github.com/mercury) has been added as a beta feature. This still allows the developer full control over markup and styling, but allows them to define editable regions of text. A simple [Rails](http://rubyonrails.org) helper is used to find the correct text from the database. Placeholder text is automatically generated for development use.

![Editing a page with Mercury Editor](/images/posts/page-edit.png)


### Setting Editable Areas

To create an editable area, the developers just need to create a normal HTML element marked up with the mercury `class` and `data-type` attributes.

Inside the editable element a simple helper is used. Content is namespaced under the page name (i.e. the basename of the `html.erb` file) and usually the `id` attrubute of the editable HTML element.

{% highlight erb %}
<div id="what-is-the-agm" class="mercury-region" data-type="editable">
  <%= content_for_area('your-union', 'what-is-the-agm') %>
</div>
{% endhighlight %}

### Retrieving Content

A simple class method on `Content` pulls out the latest content for the area, and a helper method is used to call this from the view.

{% highlight ruby %}
module PagesHelper
  def content_for_area(page, area)
    area_content = Content.for_area(page, area)
    raw area_content.body ? area_content : "Lorem ipsum dolor sit amet"
  end
end

class Content < ActiveRecord::Base
  def self.for_area(page_name, area)
    self.find_all_by_page_name_and_area(page_name, area).last
  end
end
{% endhighlight %}
