# `CrystGLFW::MouseButton`

A `CrystGLFW::MouseButton` (or `MouseButton`, for the purposes of this guide) represents an individual mouse button on the mouse. Currently, you cannot create a `MouseButton` directly - they are created and destroyed internally.

Mouse buttons can be identified through their *labels*. A label is simply a Crystal `Symbol` that references a specific `MouseButton`. Mouse button labels are derived from the names of the constants that represent them in the GLFW specification. The list of GLFW mouse buttons can be found [here](http://www.glfw.org/docs/latest/group__buttons.html). Take the name of the constant, remove the "GLFW_" prefix, and convert it to a lowercase `Symbol` to get the label. For example:

`GLFW_MOUSE_BUTTON_1` is represented in `CrystGLFW` as `:mouse_button_1`.
`GLFW_MOUSE_BUTTON_LEFT` is `:mouse_button_left`.
`GLFW_MOUSE_BUTTON_RIGHT` is `:mouse_button_right`.

And so on and so forth.

## `is?`

You can use mouse button labels to identify instances of `MouseButton` using the `is?` method:

```crystal
window.on_mouse_button do |event|
  mouse_button = event.mouse_button
  if mouse_button.is?(:mouse_button_1)
    puts "mouse button 1"
  elsif mouse_button.is?(:mouse_button_2)
    puts "mouse button 2"
  else
    puts "other mouse button"
  end
end
```

`is?` returns `true` if the given label matches the `MouseButton`, and returns `false` otherwise.

You can pass an arbitrary number of labels, and `is?` will return `true` if any one of the labels matches the `MouseButton`:

```crystal
window.on_mouse_button do |event|
  mouse_button = event.mouse_button
  if mouse_button.is?(:mouse_button_left, :mouse_button_right, :mouse_button_middle)
    puts "Normal mouse button!"
  else
    puts "Fancy mouse button!"
  end
end
```

All `MouseButton` functionality must be called from within a [`run`](/the-run-block.md) block definition.