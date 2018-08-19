---
layout: post
title: Redirect To Next Action in Rails
meta: Redirect to a different next action in Ruby on Rails
---

# {{ page.title }}

Here's a simple way of redirecting to a different page depending on the previous page in Rails.

Lets say you want to redirect to a different action depending on where the user publishes an article.

In your view, set the `:next_action` parameter in the `link_to` helper.

```erb
<!-- admin/articles/show.html.erb -->
<%= link_to 'Publish', publish_article_path(:next_action => article_path(@article)) %>

<!-- admin/articles/index.html.erb -->
<%= link_to 'Publish', publish_article_path(:next_action => articles_path) %>
```

In the controller you can check whether the `:next_action` parameter exists, or fall back to a default.

```ruby
# ArticlesController#publish
def publish
  # ...
  redirect_to params.fetch(:next_action, articles_path)
end
```

The `fetch` method will take the value of `params[:next_action]` if it exists, otherwise will fall back to the second argument.

You can carry the parameter through multiple actions (e.g. `cart --> log in --> checkout`) through hidden fields in forms

```erb
<!-- sessions/new.html.erb -->
<%= f.hidden_field :next_action, params[:next_action] %>
```

or in the submit action of a form.

```erb
<!-- sessions/new.html.erb -->
<%= form_for :model, :url => model_path(@model, :next_action => custom_action_path) do |f| %>
```
