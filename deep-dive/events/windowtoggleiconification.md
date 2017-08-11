# `CrystGLFW::Event::WindowToggleIconification`

A `CrystGLFW::Event::WindowToggleIconification` is generated when a [`Window`](/deep-dive/window.md) is either iconified or restored. It is yielded to the block defined by [`on_toggle_iconification`](/deep-dive/window/callbacks/on-toggle-iconification.md).

```crystal
window = Window.new

window.on_toggle_iconification do |event|
  if event.iconified?
    puts "Window is iconified!"
  else
    puts "Window is restored!"
  end
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `iconified?`

You can determine whether or not the [`Window`](/deep-dive/window.md) was iconified using the `iconified?` method:

```crystal
event.iconified?
```

`iconified?` returns `true` if the [`Window`](/deep-dive/window.md) was iconified, and returns `false` if the [`Window`](/deep-dive/window.md) was restored.