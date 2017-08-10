# `on_cursor_cross_threshold`

The `on_cursor_cross_threshold` method defines callback behavior that is triggered when the system cursor either enters or exits a `Window`. It generates a [`CrystGLFW::Event::WindowCursorCrossThreshold`](/deep-dive/events/windowcursorcrossthreshold.md) that is yielded to the block:

```crystal
window = Window.new

window.on_cursor_cross_threshold do |event|
  if event.entered?
    puts "cursor entered window"
  else
    puts "cursor exited window"
  end
end
```

With this callback defined, every time the cursor enters or exits `window`, the appropriate message is printed to standard output.

`on_cursor_cross_threshold` must be called from within a `run` block definition.