---
layout: post
title: Tile images using the command line
meta: How to use montage from the ImageMagick CLI tools to tile images in horizontal, vertical and 2up layouts.
---

# {{ page.title }}

I often want to join a couple of screenshots together in one image to illustrate a user journey or to show before and after user interfaces.

[Last year](https://twitter.com/_gareth/status/1127500331254984705) I learned you can do this using [`montage`](https://www.imagemagick.org/Usage/montage/) from the ImageMagick CLI tools, but even now I still forget the exact geometry options to use to get the layout I want.

To fix this, I recently wrote a [small wrapper](https://github.com/garethrees/dotfiles/blob/master/bin/tile) around `montage` to make it easier to create the montages I most frequently use.

# Horizontal Tiling

```sh
$ tile horizontal a.png b.png horizontal.jpg
```

![Images tiled horizontally](/images/posts/horizontal.jpg)

```sh
# montage equivalent
$ montage -width 800 -tile x1 a.png b.png horizontal.jpg
```

# Vertical Tiling

```sh
$ tile vertical a.png b.png vertical.jpg
```

![Images tiled vertically](/images/posts/vertical.jpg)

```sh
# montage equivalent
$ montage -width 800 -tile 1x a.png b.png vertical.jpg
```

# 2-up Tiling

```sh
$ tile 2up a.png b.png b.png a.png 2up.jpg
```

![Images tiled 2up](/images/posts/2up.jpg)

```sh
# montage equivalent
$ montage -width 800 -tile 2x a.png b.png b.png a.png 2up.jpg
```

# 2-up Tiling of a Single Image

```sh
$ tile 2up a.png 2up-single.jpg
```

![Single image using 2up layout to give space for annotations](/images/posts/2up-single.jpg)

```sh
# montage equivalent
$ montage -width 800 -tile 2x a.png 2up-single.jpg
```

Using the `2up` layout with a single input image has a particularly nice side effect of rendering blank space where a second input image would have been. You can use this space to add annotations.

## Setting the Width

[`tile`](https://github.com/garethrees/dotfiles/blob/master/bin/tile) automatically resizes all images to 800px wide. This is usually about the width that’s most useful for me. It’s big enough to be able to see most details, but small enough to use inline in an email.

The resizing is applied to the input images, rather than the output image. You'll notice that the relative zoom of the [vertical](#vertical-tiling) image above is higher. If we wanted to maintain the relative size of each image, it’s easy to do with the `-w` flag.

```sh
$ tile -w 400 vertical a.png b.png vertical-400.jpg
```

![Images tiled vertically at 400px wide](/images/posts/vertical-400.jpg)


```sh
# montage equivalent
$ montage -width 400 -tile 1x a.png b.png vertical-400.jpg
```

## Default Layout

[`tile`](https://github.com/garethrees/dotfiles/blob/master/bin/tile) uses the `2up` layout by default.

```sh
$ tile a.png b.png 2up.jpg
```

---

You’ll also have probably noticed that `montage` automatically converts from `png` to `jpg` by simply specifying the output format you want. Magick!

There’s [a lot](https://medium.com/@jorinvo/edit-images-on-the-command-line-with-graphicsmagick-fb53bc62d078) [more](https://hackernoon.com/save-time-by-transforming-images-in-the-command-line-c63c83e53b17) you can do with ImageMagick on the command line, but merging images together into a tiled layout is my most-used feature, and it’s much easier with montage compared to any of the default Apple image editing tools.

[Let me know](https://twitter.com/_gareth/) if you have any feedback.
