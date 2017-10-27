# `CrystGLFW::Event::WindowMove`

A `CrystGLFW::Event::WindowMove` is generated when a [`Window`](/deep-dive/window.md) is moved. It is yielded to the block defined by [`on_move`](/deep-dive/window/callbacks/on-move.md).

```crystal
window = Window.new

window.on_move do |event|
  puts "window moved to #{event.position}"
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `position`

You can retrieve the new coordinates of the [`Window`](/deep-dive/window.md) using the `position` method:

```crystal
event.position # => {x: Int32, y: Int32}
```