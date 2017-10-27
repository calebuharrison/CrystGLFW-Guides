# `CrystGLFW::Event::WindowCursorMove`

A `CrystGLFW::Event::WindowCursorMove` is generated when the system cursor is moved while a [`Window`](/deep-dive/window.md) has input focus. It is yielded to the block defined by [`on_cursor_move`](/deep-dive/window/callbacks/on-cursor-move.md).

```crystal
window = Window.new

window.on_cursor_move do |event|
  puts "cursor moved to #{event.position}"
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `cursor`

You can retrieve the [`Cursor`](/deep-dive/window/cursors.md) associated with the [`Window`](/deep-dive/window.md) using the `cursor` method:

```crystal
event.cursor # => CrystGLFW::Cursor
```

## `position`

You can retrieve the new coordinates of the cursor using the `position` method:

```crystal
event.position # => {x: Float64, y: Float64}
```
