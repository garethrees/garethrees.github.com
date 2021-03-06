---
layout: post
title: Testing flash.keep in Rails 3.2
---

# {{ page.title }}

[Mike Naberenzy](http://mikenaberezny.com/2007/09/08/keep-the-flash-and-test-it-too/) once posted about testing `flash.keep` in Rails. His method doesn't seem to work
since Rails 2.1.

Here's how I got a passing spec.

```ruby
it 'keeps the search_params flash' do
  # Make two get requests to simulate the flash getting swept after the
  # first response.
  get :something, nil, nil, :foo => 'bar'
  get :something
  expect(flash[:foo]).to eq('bar')
end
```

With an empty controller, the spec fails.

```ruby
class SomethingController < ApplicationController
  def something

  end
end
```

Keeping the flash allows the spec to pass:

```ruby
class SomethingController < ApplicationController
  def something
    flash.keep(:foo)
  end
end
```
