# `on_cursor_move`

The `on_cursor_move` method defines callback behavior that is triggered when the system cursor is moved while a [`Window`](/deep-dive/window.md) has input focus. It generates a [`CrystGLFW::Event::WindowCursorMove`](/deep-dive/events/windowcursormove.md) that is yielded to the block:

```crystal
window = Window.new

window.on_cursor_move do |event|
  puts "cursor moved to #{event.position}"
end
```

With this callback defined, every time the cursor is moved while `window` has input focus, the cursor's new location (relative to `window`) is printed to standard output.

`on_cursor_move` must be called from within a [`run`](/the-run-block.md) block definition.