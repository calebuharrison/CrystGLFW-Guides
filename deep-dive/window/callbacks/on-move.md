# `on_move`

The `on_move` method defines callback behavior that is triggered when a [`Window`](/deep-dive/window.md) is moved. It generates a [`CrystGLFW::Event::WindowMove`](/deep-dive/events/windowmove.md) that is yielded to the block:

```crystal
window = Window.new

window.on_move do |event|
  puts "window moved to (#{event.x}, #{event.y})"
end
```

With this callback defined, every time `window` is moved, its new location is printed to standard output.

`on_move` must be called from within a `run` block definition.