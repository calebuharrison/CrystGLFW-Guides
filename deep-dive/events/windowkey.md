# `CrystGLFW::Event::WindowKey`

A `CrystGLFW::Event::WindowKey` is generated when a key is pressed/released/held while a `Window` has input focus. It is yielded to the block defined by `on_key`.

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

## `window`

You can retrieve the event's associated `Window` using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `key`

You can retrieve the `Key` that was pressed/released/held using the `key` method:

```crystal
event.key # => CrystGLFW::Key
```

## `press?`, `release?`, and `repeat?`

You can check what kind of action was performed on the key using `press?`, `release?` and `repeat?`:

```crystal
if event.press?
  puts "key was pressed"
elsif event.release?
  puts "key was released"
elsif key.repeat?
  puts "key was held down"
else
  puts "impossible!"
end
```

## Modifiers

You can also use any of the methods from the [`Modifiers`](/deep-dive/modifiers.md) module on a `CrystGLFW::Event::WindowKey`.