# `CrystGLFW::Event::WindowScroll`

A `CrystGLFW::Event::WindowScroll` is generated when the user scrolls while a [`Window`](/deep-dive/window.md) has input focus. It is yielded to the block defined by [`on_scroll`](/deep-dive/window/callbacks/on-scroll.md).

```crystal
window = Window.new

window.on_scroll do |event|
  puts "scroll offset: #{event.offset}"
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `offset`

You can retrieve the scroll offset using the `offset` method:

```crystal
event.offset # => {x: Float64, y: Float64}
```