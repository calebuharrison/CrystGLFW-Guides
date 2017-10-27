# `CrystGLFW::MouseButton`

A `CrystGLFW::MouseButton` (or `MouseButton`, for the purposes of this guide) represents an individual mouse button on the mouse. Internally, `MouseButton` is implemented as a Crystal Enum.

Mouse button member names are derived from the names of the constants that represent them in the GLFW specification. The list of GLFW mouse buttons can be found [here](http://www.glfw.org/docs/latest/group__buttons.html). Take the name of the constant, remove the "GLFW_MOUSE_BUTTON_" prefix and replace it with "MouseButton::", and convert the rest to UpperCamelCase to get the name. For example:

`GLFW_MOUSE_BUTTON_LEFT` is represented in `CrystGLFW` as `MouseButton::Left`.
`GLFW_MOUSE_BUTTON_RIGHT` is `MouseButton::Right`.
`GLFW_MOUSE_BUTTON_MIDDLE` is `MouseButton::Middle`.

And so on and so forth. A drawback of this approach is that mouse button names that begin with a number must have that number spelled out:

`GLFW_MOUSE_BUTTON_1` is represented in `CrystGLFW` as `MouseButton::One`.

## Checking Mouse Buttons

Because `MouseButton` is an Enum, question methods are available for each possible value of a given `MouseButton`:

```crystal
window.on_mouse_button do |event|
  mouse_button = event.mouse_button
  if mouse_button.one?
    puts "mouse button 1"
  elsif mouse_button.two?
    puts "mouse button 2"
  elsif mouse_button.left?
    puts "left mouse button"
  else
    puts "other mouse button"
  end
end
```