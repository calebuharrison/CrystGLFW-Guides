# `CrystGLFW::Event::WindowResize`

A `CrystGLFW::Event::WindowResize` is generated when a [`Window`](/deep-dive/window.md) is resized. It is yielded to the block defined by [`on_resize`](/deep-dive/window/callbacks/on-resize.md).

```crystal
window = Window.new

window.on_resize do |event|
  puts "window resized to #{event.width}x#{event.height}"
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `width` and `height`

You can retrieve the new size of the [`Window`](/deep-dive/window.md) using the `width` and `height` methods:

```crystal
event.width # => Int32
event.height # => Int32
```