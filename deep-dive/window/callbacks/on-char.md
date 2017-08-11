# `on_char`

The `on_char` method defines callback behavior that is triggered when a character is input while a [`Window`](/deep-dive/window.md) has input focus. It generates a [`CrystGLFW::Event::WindowChar`](/deep-dive/events/windowchar.md) that is yielded to the block:

```crystal
window = Window.new

window.on_char do |event|
  puts "user input: #{event.char}"
end
```

With this callback defined, every time a character is input while `window` has input focus, the character is printed to standard output.

`on_char` must be called from within a [`run`](/the-run-block.md) block definition.