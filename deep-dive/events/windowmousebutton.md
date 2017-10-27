# `CrystGLFW::Event::WindowMouseButton`

A `CrystGLFW::Event::WindowMouseButton` is generated when a mouse button is pressed/released while a [`Window`](/deep-dive/window.md) has input focus. It is yielded to the block defined by [`on_mouse_button`](/deep-dive/window/callbacks/on-mouse-button.md).

```crystal
window = Window.new

window.on_mouse_button do |event|
  mouse_button = event.mouse_button
  if event.action.press? && mouse_button.left?
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

## `action`

You can retrieve the [Action](/action.md) that was performed using the `action` method:

```crystal
if event.action.press?
  puts "mouse button was pressed"
elsif event.action.release?
  puts "mouse button was released"
else
  puts "impossible!"
end
```

## Modifiers

You can also use any of the methods from the [`Modifiers`](/deep-dive/modifiers.md) module on a `CrystGLFW::Event::WindowMouseButton`.
