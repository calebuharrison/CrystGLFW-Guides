# `CrystGLFW::Event::WindowFramebufferResize`

A `CrystGLFW::Event::WindowFramebufferResize` is generated when the frame buffer of a `Window` is resized. It is yielded to the block defined by `on_framebuffer_resize`.

```crystal
window = Window.new

window.on_framebuffer_resize do |event|
  puts "frame buffer resized to #{event.width}x#{event.height}"
end
```

## `window`

You can retrieve the event's associated `Window` using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `width` and `height`

You can retrieve the new size of the frame buffer using the `width` and `height` methods:

```crystal
event.width # => Int32
event.height # => Int32
```