# CrystGLFW::Window::Image

A `CrystGLFW::Window::Image` (or `Image` for the purposes of this guide) can be used both for a custom cursor image and for a window's icon.

You can create an `Image` with the `new` method:

```crystal
width, height = 16, 16
white = 255
pixels = Array(UInt8).new(width * height, white)
image = CrystGLFW::Window::Image.new(width, height, pixels)
```

The initializer takes the following arguments:
- *width*, the width of the image, in pixels.
- *height*, the height of the image, in pixels.
- *pixels*, an `Array(UInt8)` that should be *width x height* in length.

You'll need to use another library to extract the pixel data from various image formats. The pixel data in *pixels* should be arranged left-to-right, top-to-bottom.

## `width`, `height`, and `pixels`

`Image` has only three public methods, each of which merely expose the attributes given to it upon initialization:

```crystal
width, height = 16, 16
white = 255
pixels = Array(UInt8).new(width * height, white)
image = CrystGLFW::Window::Image.new(width, height, pixels)

image.width # => 16
image.height # => 16
image.pixels # => Array(UInt8)
```

`width`, `height`, and `pixels` must be called from within a `run` block definition.