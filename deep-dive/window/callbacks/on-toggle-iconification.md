# `on_toggle_iconification`

The `on_toggle_iconification` method defines callback behavior that is triggered when a window's "iconification" is toggled. This occurs either when a [`Window`](/deep-dive/window.md) is iconified or restored. It generates a [`CrystGLFW::Event::WindowToggleIconification`](/deep-dive/events/windowtoggleiconification.md) that is yielded to the block:

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

With this callback defined, every time the iconification of `window` is toggled, it prints whether or not it is iconified to standard output.

`on_toggle_iconification` must be called from within a [`run`](/the-run-block.md) block definition.