# `on_mouse_button`

The `on_mouse_button` method defines callback behavior that is triggered when a mouse button is pressed/released while a `Window` has input focus. It generates a [`CrystGLFW::Event::WindowMouseButton`](/deep-dive/events/windowmousebutton.md) that is yielded to the block:

```crystal
window = Window.new

window.on_mouse_button do |event|
  mouse_button = event.mouse_button
  if mouse_button.press? && mouse_button.is? :mouse_button_left
    puts "the left mouse button was clicked"
  end  
end
```

With this callback defined, every time the left mouse button is clicked while `window` has input focus, "the left mouse button was clicked" is printed to standard output.

`on_mouse_button` must be called from within a `run` block definition.