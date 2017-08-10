# `CrystGLFW::Event::WindowToggleFocus`

A `CrystGLFW::Event::WindowToggleFocus` is generated when the input focus of a `Window` is toggled. It is yielded to the block defined by `on_toggle_focus`.

```crystal
window = Window.new

window.on_toggle_focus do |event|
  if event.focused?
    puts "Window is focused!"
  else
    puts "Window is out of focus!"
  end
end
```

## `window`

You can retrieve the event's associated `Window` using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `focused?`

You can determine whether or not the `Window` was focused using the `focused?` method:

```crystal
event.focused?
```

`focused?` returns `true` if the `Window` gained focus, and returns `false` if the `Window` lost focus.