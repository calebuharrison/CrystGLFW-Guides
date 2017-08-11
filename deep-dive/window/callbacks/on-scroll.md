# `on_scroll`

The `on_scroll` method defines callback behavior that is triggered when the user scrolls while a [`Window`](/deep-dive/window.md) has input focus. It generates a [`CrystGLFW::Event::WindowScroll`](/deep-dive/events/windowscroll.md) that is yielded to the block:

```crystal
window = Window.new

window.on_scroll do |event|
  puts "scroll offset: (#{event.x}, #{event.y})"
end
```

With this callback defined, every time the user scrolls while `window` has input focus, the scroll offset is printed to standard output.

`on_scroll` must be called from within a [`run`](/the-run-block.md) block definition.