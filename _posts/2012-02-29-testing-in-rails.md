---
layout: post
title: Testing in Rails
meta: A guide to the different types of testing in Rails
---

# {{ page.title }}

I've been using [Rails](http://rubyonrails.org) for over 2 years now, but testing has only really clicked with me much more recently.

In University the most we delved in to testing was to have a list of features and a box to tick if you think they work as expected.

## Testing Libraries

* Test::Unit
* RSpec
* Minitest

## Types of Testing

### Unit Testing

Unit testing is performed on the methods in a `Class`. We test each method to make sure that we know the building blocks of our application perform as expected.

It's not unusal to perform several tests on one method to ensure edge cases do not break the method.

Unit tests are usually written by developers as they work on the code.

* [Unit testing in Test:Unit](http://guides.rubyonrails.org/testing.html#unit-testing-your-models)
* [Model testing in Rspec](https://www.relishapp.com/rspec/rspec-rails/docs/model-specs)
* [Unit testing in Minitest](http://docs.seattlerb.org/minitest/MiniTest/Unit/TestCase.html)

### Functional Testing

Functional testing is performed at the `Controller` level to ensure the incoming web request responds appropriately.

* [Functional testing in Test:Unit](http://guides.rubyonrails.org/testing.html#functional-tests-for-your-controllers)
* [Controller testing in Rspec](https://www.relishapp.com/rspec/rspec-rails/docs/controller-specs)
* [Controller Spec testing in Minitest](http://docs.seattlerb.org/minitest/MiniTest/Spec.html)

### Integration Testing

* [Integration testing in Test:Unit](http://guides.rubyonrails.org/testing.html#integration-testing)
* [Request Specs in Rspec](https://www.relishapp.com/rspec/rspec-rails/v/2-8/docs/request-specs/request-spec)
* [Controller Spec testing in Minitest](http://docs.seattlerb.org/minitest/MiniTest/Spec.html)
