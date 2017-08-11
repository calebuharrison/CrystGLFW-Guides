# `on_refresh`

The `on_refresh` method defines callback behavior that is triggered when a [`Window`](/deep-dive/window.md) is refreshed. It generates a [`CrystGLFW::Event::WindowRefresh`](/deep-dive/events/windowrefresh.md) that is yielded to the block:

```crystal
window = Window.new

window.on_refresh do |event|
  puts "window refreshed!"
end
```

With this callback defined, every time `window` is refreshed, it prints "window refreshed!" to standard output.

`on_refresh` must be called from within a [`run`](/the-run-block.md) block definition.