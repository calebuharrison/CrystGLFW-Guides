# `on_toggle_focus`

The `on_toggle_focus` method defines callback behavior that is triggered when a window's "focus" is toggled. It generates a [`CrystGLFW::Event::WindowToggleFocus`](/deep-dive/events/windowtogglefocus.md) that is yielded to the block:

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

With this callback defined, every time the focus of `window` is toggled, it prints whether or not it is focused to standard output.

`on_toggle_focus` must be called from within a [`run`](/the-run-block.md) block definition.