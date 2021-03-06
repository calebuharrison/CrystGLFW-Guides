# `CrystGLFW::Event::WindowFramebufferResize`

A `CrystGLFW::Event::WindowFramebufferResize` is generated when the frame buffer of a [`Window`](/deep-dive/window.md) is resized. It is yielded to the block defined by [`on_framebuffer_resize`](/deep-dive/window/callbacks/on-framebuffer-resize.md).

```crystal
window = Window.new

window.on_framebuffer_resize do |event|
  puts "frame buffer resized to #{event.size}"
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `size`

You can retrieve the new size of the frame buffer using the `size` method:

```crystal
event.size # => {width: Int32, height: Int32}
```