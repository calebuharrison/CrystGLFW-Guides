# Sticky Mouse Buttons

"Sticky Mouse Buttons" is an input mode that forces `mouse_button_pressed?` to return `true`  the first time it is called *after* the passed `MouseButton` has been pressed, *regardless* of whether or not the `MouseButton` is still pressed.

## `sticky_mouse_buttons?`

You can see if a `Window` currently has sticky mouse buttons enabled with the `sticky_mouse_buttons?` method:

```crystal
window = Window.new
window.sticky_mouse_buttons? # => false
```

`sticky_mouse_buttons?` returns `true` if sticky mouse buttons are enabled, and returns `false` otherwise.

`sticky_mouse_buttons?` must be called from within a `run` block definition.

## `enable_sticky_mouse_buttons` and `disable_sticky_mouse_buttons`

You can enable sticky mouse buttons with the `enable_sticky_mouse_buttons` method:

```crystal
window = Window.new
window.sticky_mouse_buttons? # => false

window.enable_sticky_mouse_buttons
window.sticky_mouse_buttons? # => true
```

You can also disable sticky mouse buttons with `disable_sticky_mouse_buttons`:

```crystal
window.sticky_mouse_buttons? # => true

window.disable_sticky_mouse_buttons
window.sticky_mouse_buttons? # => false
```

Both `enable_sticky_mouse_buttons` and `disable_sticky_mouse_buttons` must be called from within a `run` block definition.

