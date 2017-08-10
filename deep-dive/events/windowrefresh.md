# `CrystGLFW::Event::WindowRefresh`

A `CrystGLFW::Event::WindowRefresh` is generated when a `Window` is closed. It is yielded to the block defined by `on_refresh`.

```crystal
window = Window.new

window.on_refresh do |event|
  puts "window refreshed!"
end
```

## `window`

You can retrieve the event's associated `Window` using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```