# `on_key`

The `on_key` method defines callback behavior that is triggered when a key is pressed/released/held while a `Window` has input focus. It generates a [`CrystGLFW::Event::WindowKey`](/deep-dive/events/windowkey.md) that is yielded to the block:

```crystal
window = Window.new

window.on_key do |event|
  key = event.key
  if event.press?
    if key.printable?
      puts "#{key.name} was pressed"
    else
      puts "an unprintable key was pressed"
    end
  end  
end
```

With this callback defined, every time a key is pressed while `window` has input focus, the key's name is printed to standard output if the key is printable.

`on_key` must be called from within a `run` block definition.