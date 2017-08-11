# `CrystGLFW::Event::WindowScroll`

A `CrystGLFW::Event::WindowScroll` is generated when the user scrolls while a [`Window`](/deep-dive/window.md) has input focus. It is yielded to the block defined by [`on_scroll`](/deep-dive/window/callbacks/on-scroll.md).

```crystal
window = Window.new

window.on_scroll do |event|
  puts "scroll offset: (#{event.x}, #{event.y})"
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `x` and `y`

You can retrieve the scroll offset using the `x` and `y` methods:

```crystal
event.x # => Int32
event.y # => Int32
```