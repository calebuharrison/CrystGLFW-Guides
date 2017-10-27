# `CrystGLFW::Event::WindowResize`

A `CrystGLFW::Event::WindowResize` is generated when a [`Window`](/deep-dive/window.md) is resized. It is yielded to the block defined by [`on_resize`](/deep-dive/window/callbacks/on-resize.md).

```crystal
window = Window.new

window.on_resize do |event|
  puts "window resized to #{event.size}"
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `size`

You can retrieve the new size of the [`Window`](/deep-dive/window.md) using the `size` method:

```crystal
event.size # => {width: Int32, height: Int32}
```