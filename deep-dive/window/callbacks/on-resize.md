# `on_resize`

The `on_resize` method defines callback behavior that is triggered when a `Window` is resized. It generates a [`CrystGLFW::Event::WindowResize`](/deep-dive/events/windowresize.md) that is yielded to the block:

```crystal
window = Window.new

window.on_resize do |event|
  puts "window resized to #{event.width}x#{event.height}"
end
```

With this callback defined, every time `window` is resized, its new dimensions are printed to standard output.

`on_resize` must be called from within a `run` block definition.