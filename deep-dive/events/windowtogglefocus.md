# `CrystGLFW::Event::WindowToggleFocus`

A `CrystGLFW::Event::WindowToggleFocus` is generated when the input focus of a [`Window`](/deep-dive/window.md) is toggled. It is yielded to the block defined by [`on_toggle_focus`](/deep-dive/window/callbacks/on-toggle-focus.md).

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

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `focused?`

You can determine whether or not the [`Window`](/deep-dive/window.md) was focused using the `focused?` method:

```crystal
event.focused?
```

`focused?` returns `true` if the [`Window`](/deep-dive/window.md) gained focus, and returns `false` if the [`Window`](/deep-dive/window.md) lost focus.