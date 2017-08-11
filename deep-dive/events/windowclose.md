# `CrystGLFW::Event::WindowClose`

A `CrystGLFW::Event::WindowClose` is generated when a [`Window`](/deep-dive/window.md) is closed. It is yielded to the block defined by [`on_close`](/deep-dive/window/callbacks/on-close.md).

```crystal
window = Window.new

window.on_close do |event|
  puts "Bye!"
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```