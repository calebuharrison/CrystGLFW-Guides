# `CrystGLFW::Event::WindowScroll`

A `CrystGLFW::Event::WindowScroll` is generated when the user scrolls while a `Window` has input focus. It is yielded to the block defined by `on_scroll`.

```crystal
window = Window.new

window.on_scroll do |event|
  puts "scroll offset: (#{event.x}, #{event.y})"
end
```

## `window`

You can retrieve the event's associated `Window` using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `x` and `y`

You can retrieve the scroll offset using the `x` and `y` methods:

```crystal
event.x # => Int32
event.y # => Int32
```