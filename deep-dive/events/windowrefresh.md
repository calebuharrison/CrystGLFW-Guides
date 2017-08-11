# `CrystGLFW::Event::WindowRefresh`

A `CrystGLFW::Event::WindowRefresh` is generated when a [`Window`](/deep-dive/window.md)is closed. It is yielded to the block defined by [`on_refresh`](/deep-dive/window/callbacks/on-refresh.md).

```crystal
window = Window.new

window.on_refresh do |event|
  puts "window refreshed!"
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```