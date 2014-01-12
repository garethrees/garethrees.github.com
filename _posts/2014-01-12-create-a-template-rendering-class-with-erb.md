---
layout: post
title: Create a template rendering class with ERB
---

# {{ page.title }}

I've often wanted to create a class which generates some text from a template. I've had a go at this [using Mustache](https://github.com/garethrees/paramsfile) but this time I wanted to see what can be done with [ERB](http://ruby-doc.org/stdlib-2.1.0/libdoc/erb/rdoc/ERB.html).

## Just show me the code!

Here's what we'll end up with.
Source available [on GitHub](https://gist.github.com/garethrees/8386142).

{% highlight ruby %}
class WelcomeMessage < ERB

  def self.template
    "Welcome, <%= @name %>"
  end

  def initialize(name, options = {})
    @name     = name
    @template = options.fetch(:template, self.class.template)
    super(@template)
  end

  def result
    super(binding)
  end

end
{% endhighlight %}

## How ERB Works

First, I took a look at [how Ruby's ERB templating system works](http://rrn.dk/rubys-erb-templating-system).

It's pretty simple.

{% highlight ruby %}
require 'erb'

name            = "Gareth"
template_string = "My name is <%= name %>"
template        = ERB.new(template_string)
template.result
# => prints "My name is Gareth"
{% endhighlight %}

So we can see all that's needed to create a new instance of `ERB` is the template in the form of a `String`, and then call `result` in order to render the template and interpolate any variables.

Notice that `name` is a variable in the top level context of `self`.

> The binding is a pointer to a set of local variables. If no binding is given, the top level binding will be used, which is why <%= name %> gets evaluated as "Gareth" in the above example.

We can pass a [`Binding`](http://ruby-doc.org/core-2.1.0/Binding.html) object to `ERB#render` to access a different set of variables.

{% highlight ruby %}
require 'erb'

class DummyController
  def index
    @name = 'Gareth'
  end

  # This is only a helper method to access
  # the object's (private) binding method
  def get_binding
    binding
  end
end

controller = DummyController.new
controller.index

template_string = "Welcome <%= @name %>"
template        = ERB.new(template_string)
template.result(controller.get_binding)
# => "Welcome Gareth"
{% endhighlight %}

## Subclassing ERB

What I really wanted was a class that could return a rendered template itself.

First, I defined how I wanted to interact with the class and sketched a template of the public methods I'd need.

{% highlight ruby %}
# Example usage
msg = WelcomeMessage.new('Gareth')
msg.result
# => "Welcome, Gareth"

# Sketch outline of class
class WelcomeMessage < ERB

  def initialize(name)
    # store the name of the person to greet
  end

  def result
    # render the template
  end

end
{% endhighlight %}

### Setting up the data

After storing the name in an instance variable, the next step was picking the template to render. As we know, `ERB` itself takes the template string as an argument to `initialize`. We can pass this up the chain by calling `super` with the template. I set a default at the class level and allowed an option to be passed when creating a new instance of the class.

{% highlight ruby %}
class WelcomeMessage < ERB

  def self.template
    "Welcome, <%= @name %>"
  end

  def initialize(name, options = {})
    @name     = name
    @template = options.fetch(:template, self.class.template)
    super(@template)
  end

end

# Use the default template
msg = WelcomeMessage.new('Gareth')
msg.instance_variable_get(:@template)
# => "Welcome, <%= @name %>"

# Use a custom template
msg = WelcomeMessage.new('Gareth', template: "Hello, <%= @name %>") msg.instance_variable_get(:@template)
# => "Hello, <%= @name %>"
{% endhighlight %}  

Now we need to interpolate the variables in to the template and render it. To make the API consistent with `ERB`, we'll override `ERB#result` to always pass the binding as a parameter.

{% highlight ruby %}
def result
  super(binding)
end
{% endhighlight %}

Now we can use the new class to render our template!

{% highlight ruby %}
msg = WelcomeMessage.new('Gareth')
msg.result
# => "Welcome, Gareth"
{% endhighlight %}

## Notes

- You can clone/fork the source code [on GitHub](https://gist.github.com/garethrees/8386142)
- I used these principles to create a Sinatra app that [generates an nginx server configuration file](https://github.com/garethrees/nginx-server-generator)
