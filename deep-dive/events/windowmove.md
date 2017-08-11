# `CrystGLFW::Event::WindowMove`

A `CrystGLFW::Event::WindowMove` is generated when a [`Window`](/deep-dive/window.md) is moved. It is yielded to the block defined by [`on_move`](/deep-dive/window/callbacks/on-move.md).

```crystal
window = Window.new

window.on_move do |event|
  puts "window moved to (#{event.x}, #{event.y})"
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `x` and `y`

You can retrieve the new coordinates of the [`Window`](/deep-dive/window.md) using the `x` and `y` methods:

```crystal
event.x # => Int32
event.y # => Int32
```