# `CrystGLFW::Event::WindowMouseButton`

A `CrystGLFW::Event::WindowMouseButton` is generated when a mouse button is pressed/released while a [`Window`](/deep-dive/window.md) has input focus. It is yielded to the block defined by [`on_mouse_button`](/deep-dive/window/callbacks/on-mouse-button.md).

```crystal
window = Window.new

window.on_mouse_button do |event|
  mouse_button = event.mouse_button
  if event.press? && mouse_button.is? :mouse_button_left
    puts "the left mouse button was clicked"
  end  
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `mouse_button`

You can retrieve the [`MouseButton`](/deep-dive/mouse-buttons.md) that was pressed/released using the `mouse_button` method:

```crystal
event.mouse_button # => CrystGLFW::MouseButton
```

## `press?` and `release?`

You can check what kind of action was performed on the key using `press?` and `release?`:

```crystal
if event.press?
  puts "mouse button was pressed"
elsif event.release?
  puts "mouse button was released"
else
  puts "impossible!"
end
```

## Modifiers

You can also use any of the methods from the [`Modifiers`](/deep-dive/modifiers.md) module on a `CrystGLFW::Event::WindowMouseButton`.
