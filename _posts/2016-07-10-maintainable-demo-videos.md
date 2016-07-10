---
layout: post
title: Maintainable Demo Videos
meta: Automate demo video creation with RSpec and Headless

---

# {{ page.title }}

After a work meetup I was thinking about onboarding and how nice it would be to have demo videos of our products. Even if they are short and sweet, keeping them up to date can be hard work.

In Alaveteli, we have a handful of integration specs that test some core workflows through a fake web browser. This gives us confidence that the main functionality is still working when we're making code changes. These specs are always kept up to date with changes in the code.

We use Capybara to give us a really nice DSL for writing these integration tests:

```ruby
scenario 'Signing in with correct credentials' do
  visit '/sessions/new'
  within('#session') do
    fill_in 'Email', :with => 'user@example.com'
    fill_in 'Password', :with => 'caplin'
  end
  click_button 'Sign in'
  expect(page).to have_content 'Success'
end
```

So we have these nice human readable specs that actually walk through a browser, filling in the forms and clicking buttons. Surely we can get a bit more out of this?

Turns out someone's [already thought about it](https://github.com/leonid-shevtsov/headless).

TL;DR: Headless captures video of the test in action.

Here's an integration spec that tests the process of landing on an Alaveteli, making a request as an unregistered user:

```ruby
describe 'Creating a request' do
  it 'allows a new user to create an account and make a request' do
    visit frontpage_path

    within '#navigation' do
      click_link 'Make a request'
    end

    within '#search_form' do
      fill_in 'query', :with => 'Department for Humpadinking'
      click_button 'Search'
    end

    within '#authority_search_ahead_results' do
      click_link 'Department for Humpadinking'
    end

    within '.authority__header__action-bar' do
      click_link 'Make a request to this authority'
    end

    within '#request_form' do
      fill_in 'Summary:', :with => 'A test request 123'
      fill_in 'Your request', :with => users(:bob_smith_user).email
      fill_in 'Password:', :with => 'jonespassword'
      click_button 'Sign in'
    end

    expect(page).to have_content('Your Freedom of Information request has been sent')
    expect(page).to have_content('A test request 123')
  end
end
```

With a little configuration, we can record this spec:

```ruby
describe 'Creating a request' do
  before do
    get_fixtures_xapian_index
    @headless = Headless.new(:video => {
      :provider => 'ffmpeg',
      :provider_binary_path => '/home/vagrant/ffmpeg-static/ffmpeg',
      :log_file_path => 'log/headless.log',
      :frame_rate => 120})
    @headless.start
    Capybara.default_driver = :selenium
    @headless.video.start_capture
  end

  after do
    @headless.video.stop_and_save('tmp/creating-a-request.mov')
  end
  
  it 'allows a new user to create an account and make a request' do
    visit frontpage_path
    # …
  end
end
```

The result?

<iframe width="420" height="315" src="https://www.youtube.com/embed/SMeOgOVvINs" frameborder="0" allowfullscreen></iframe>

Okay; its a little fast! I had a brief look in to slowing the video down and it seems doable.

I also added a bit of CSS to make it more obvious what form elements were being used during the video. I'm sure we could improve this much more:

```css
  a:active {
    background-color: red !important;
    border: 4px red solid !important;
    color: white !important;
  }
  input:focus,
  input:active {
    border: 4px red solid !important;
  }
```

Even if we can't make these in to proper demo videos, it should be possible to render the videos in to animated gifs that we can use to enrich our documentation.
