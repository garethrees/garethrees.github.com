---
layout: post
title: Automatically OCR Screenshots with Crystal & Automator
---

# {{ page.title }}

Whether it’s adding a website snapshot to a presentation, before/after comparisons for GitHub Issues and Pull Requests, or just as a quick method for saving a cropped version of an image, I take a _lot_ of screenshots.

I recently discovered [Screenotate](https://screenotate.com/), which integrates with macOS to automatically OCR images and generate a HTML counterpart page. This makes finding a particular screenshot a little easier, if you can remember some words on the page, and saves you re-typing text.

I tried it, and while I’d happily pay for it, there were a couple of issues that meant it didn’t really fit for me.

1. It creates filenames with 12 hour timestamps, which makes sorting annoying.
2. It can be a bit slow to write the image file. I have my `~/screenshots` directory in the Dock as a fan to quickly drag the latest screenshot into another app, and I’d frequently pick the previous image because the latest screenshot hadn’t written yet.
3. It creates the HTML version in the same directory as the image. This reduced the amount of actual screenshots I can see in my fan, and meant I needed to be a little more careful about the file I was selecting.
4. It only integrates with “Capture Selected Portion”, not “Capture Selected Window” or “Capture Entire Screen”. I often capture a full window for presentations.

## Doing it myself

[Screenotate](https://screenotate.com/) mentions it uses [Google's Tesseract OCR engine](https://github.com/tesseract-ocr/tesseract). I quickly found several libraries, so spent an hour getting a basic Ruby version up and running.

```ruby
#!/usr/bin/env ruby

require 'pathname'
require 'rtesseract'

class Screenshot
  def initialize(file)
    @file = file
  end

  def text
    RTesseract.new(file.to_s).to_s
  end

  def filename
    file.basename
  end

  def realpath
    file.realpath
  end

  protected

  attr_reader :file
end

class Html
  def initialize(screenshot)
    @screenshot = screenshot
  end

  def to_s
    <<~HTML
      <html>
        <head>
          <meta charset="UTF-8">
          <meta name="generator" content="ScreenshotToHtml">
          <title>#{screenshot.filename}</title>
        </head>
        <body>
          <div>
            <img src="#{screenshot.realpath}">
          </div>
          <div>
            <tt><a href="file://#{screenshot.realpath}">#{screenshot.realpath}</a></tt>
          </div>
          <div>
            <pre>#{screenshot.text}</pre>
          </div>
        </body>
      </html>
    HTML
  end

  protected

  attr_reader :screenshot
end

SCREENSHOT = Pathname.new(ARGV.shift).freeze

puts Html.new(Screenshot.new(SCREENSHOT))
```

With my proof of concept working well, I just needed to use an [Automator Folder Action](http://www.macosxautomation.com/automator/folder-action/index.html) to run the script for new items added to `~/screenshots`.

![HTML counterpart with extracted text](/images/posts/image-to-html-output.png)

This is where things got difficult. Automator doesn’t use your usual shell environment, so it didn’t have my homebrew-installed Ruby and associated gems in the `PATH`. I played around with this for a while, but in the end it just got so complicated and brittle that I gave up.

## Enter Crystal

I noticed the author of the [Ruby tesseract library](https://github.com/dannnylo/rtesseract) also wrote a [Crystal version](https://github.com/dannnylo/tesseract-ocr-crystal), which looked suspiciously similar.

I love Ruby, but it _is_ frustrating that you need a full Ruby install for a simple little CLI tool. Crystal is a compiled and statically typed language with a syntax that’s heavily inspired by Ruby. Even the [standard library](https://crystal-lang.org/api/1.2.2/) feels very similar in naming conventions and API.

It didn’t take me long to convert my Ruby script to Crystal. I literally copied Ruby version and worked my way through the compiler errors. I barely had to change anything!

```crystal
require "path"
require "tesseract-ocr"

class Image
  def initialize(image_path : Path)
    @image_path = image_path
  end

  def text
    Tesseract::Ocr.read(real_path.to_s)
  end

  def filename
    real_path.basename
  end

  def real_path
    image_path.expand.to_native
  end

  protected def image_path
    @image_path
  end
end

class Html
  def initialize(image : Image)
    @image = image
  end

  def to_s
    <<-HTML
      <html>
        <head>
          <meta charset="UTF-8">
          <meta name="generator" content="ImageToHtml">
          <title>#{image.filename}</title>
        </head>
        <body>
          <div>
            <img src="#{image.real_path}">
          </div>
          <div>
            <tt><a href="file://#{image.real_path}">#{image.real_path}</a></tt>
          </div>
          <div>
            <pre>#{image.text}</pre>
          </div>
        </body>
      </html>
    HTML
  end

  protected def image
    @image
  end
end

image = Path[ARGV.first]
puts Html.new(Image.new(image)).to_s
```

I then compiled the program to `/usr/local/bin/image-to-html` and then it was just a matter of calling it from Automator.

![OCR Screenshots with Automator Folder Action](/images/posts/ocr-screenshots-folder-action.png)

I’ve since developed the little script into a more [well-designed library](https://github.com/garethrees/image_to_html), but in essence it’s just as simple.

I don’t get some of the nice extras of Screenotate – automatically adding text to the clipboard and its integrated search – but for me this has been working much better, and I’ve learned some Crystal too!
