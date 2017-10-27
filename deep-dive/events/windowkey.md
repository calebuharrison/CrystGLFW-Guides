# `CrystGLFW::Event::WindowKey`

A `CrystGLFW::Event::WindowKey` is generated when a key is pressed/released/held while a [`Window`](/deep-dive/window.md) has input focus. It is yielded to the block defined by [`on_key`](/deep-dive/window/callbacks/on-key.md).

```crystal
window = Window.new

window.on_key do |event|
  key = event.key
  if event.action.press?
    if key.printable?
      puts "#{key.name} was pressed"
    else
      puts "an unprintable key was pressed"
    end
  end  
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `key`

You can retrieve the [`Key`](/deep-dive/keys.md) that was pressed/released/held using the `key` method:

```crystal
event.key # => CrystGLFW::Key
```

## `action`

You can retrieve the [Action](/action.md) that was performed using the `action` method:

```crystal
if event.action.press?
  puts "key was pressed"
elsif event.action.release?
  puts "key was released"
elsif key.action.repeat?
  puts "key was held down"
else
  puts "impossible!"
end
```

## Modifiers

You can also use any of the methods from the [`Modifiers`](/deep-dive/modifiers.md) module on a `CrystGLFW::Event::WindowKey`.