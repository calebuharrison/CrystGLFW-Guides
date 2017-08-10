# `on_framebuffer_resize`

The `on_framebuffer_resize` method defines callback behavior that is triggered when the frame buffer of a `Window` is resized. It generates a [`CrystGLFW::Event::WindowFramebufferResize`](/deep-dive/events/windowframebufferresize.md) that is yielded to the block:

```crystal
window = Window.new

window.on_framebuffer_resize do |event|
  puts "window frame buffer resized to #{event.width}x#{event.height}"
end
```

With this callback defined, every time `window`'s framebuffer is resized, its new dimensions are printed to standard output.

`on_framebuffer_resize` must be called from within a `run` block definition.