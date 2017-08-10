# `CrystGLFW::Event::WindowClose`

A `CrystGLFW::Event::WindowClose` is generated when a `Window` is closed. It is yielded to the block defined by `on_close`.

```crystal
window = Window.new

window.on_close do |event|
  puts "Bye!"
end
```

## `window`

You can retrieve the event's associated `Window` using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```