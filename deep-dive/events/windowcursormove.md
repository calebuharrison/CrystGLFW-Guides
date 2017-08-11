# `CrystGLFW::Event::WindowCursorMove`

A `CrystGLFW::Event::WindowCursorMove` is generated when the system cursor is moved while a `Window` has input focus. It is yielded to the block defined by `on_cursor_move`.

```crystal
window = Window.new

window.on_cursor_move do |event|
  puts "cursor moved to (#{event.x}, #{event.y})"
end
```

## `window`

You can retrieve the event's associated `Window` using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `cursor`

You can retrieve the `Cursor` associated with the `Window` using the `cursor` method:

```crystal
event.cursor # => CrystGLFW::Cursor
```

## `x` and `y`

You can retrieve the new coordinates of the cursor using the `x` and `y` methods:

```crystal
event.x # => Float64
event.y # => Float64
```
