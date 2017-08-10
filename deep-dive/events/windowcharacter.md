# `CrystGLFW::Event::WindowChar`

A `CrystGLFW::Event::WindowChar` is generated when a character is input while a `Window` has input focus. It is yielded to the block defined by `on_char`.

```crystal
window = Window.new

window.on_char do |event|
  puts "user input: #{event.char}"
end
```

## `window`

You can retrieve the event's associated `Window` using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `char`

You can retrieve the `Char` that was input using the `char` method:

```crystal
event.char # => Char
```

## Modifiers

You can also use any of the methods from the [`Modifiers`](/deep-dive/modifiers.md) module on a `CrystGLFW::Event::WindowChar`.