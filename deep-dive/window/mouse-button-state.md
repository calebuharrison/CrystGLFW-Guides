# Mouse Button State

Each individual [`Window`](/deep-dive/window.md) keeps a record of each mouse button's state - this state can either be "press" or "release." Each window maintains its own record because windows only receive information from the mouse when they have input focus. Therefore multiple windows can have different interpretations of each mouse button's state.

## `mouse_button_pressed?`

You can find out whether or not a specific [`Window`](/deep-dive/window.md) thinks a [`MouseButton`](/deep-dive/mouse-buttons.md) is currently pressed or released using the `mouse_button_pressed?` method:

```crystal
mouse_button = event.mouse_button # => CrystGLFW::MouseButton
window.mouse_button_pressed?(mouse_button) # => Bool
```

`mouse_button_pressed?` returns `true` if the [`Window`](/deep-dive/window.md) thinks that the [`MouseButton`](/deep-dive/mouse-buttons.md) is currently pressed, and returns `false` if the [`Window`](/deep-dive/window.md) thinks that the [`MouseButton`](/deep-dive/mouse-buttons.md) is currently released. The return value of this method *is* affected by [sticky mouse buttons](/deep-dive/window/sticky-mouse-buttons.md).