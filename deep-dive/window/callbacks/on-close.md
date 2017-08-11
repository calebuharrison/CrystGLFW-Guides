# `on_close`

The `on_close` method defines callback behavior that is triggered when a [`Window`](/deep-dive/window.md) is closed/destroyed. It generates a [`CrystGLFW::Event::WindowClose`](/deep-dive/events/windowclose.md) that is yielded to the block:

```crystal
window = Window.new

window.on_close do |event|
  puts "Bye!"
end
```

With this callback defined, when the `window` is closed, it will print "Bye!" to standard output.

`on_close` must be called from within a `run` block definition.