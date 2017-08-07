# Sticky Keys

"Sticky Keys" is an input mode that forces `key_pressed?` to return `true`  the first time it is called *after* the passed `Key` has been pressed, *regardless* of whether or not the `Key` is still pressed.

## `sticky_keys?`

You can see if a `Window` currently has sticky keys enabled using the `sticky_keys?` method:

```crystal
window = Window.new
window.sticky_keys? # => false
```

Obviously, `sticky_keys?` returns `true` if sticky keys are enabled, and `false` if they are disabled. They are disabled by default.

`sticky_keys?` must be called from within a `run` block definition.

## `enable_sticky_keys` and `disable_sticky_keys`

You can enable sticky keys with (go figure!) the `enable_sticky_keys` method:

```crystal
window = Window.new
window.sticky_keys? # => false

window.enable_sticky_keys
window.sticky_keys? # => true
```

You can also disable sticky keys with `disable_sticky_keys`:

```crystal
window.sticky_keys? # => true

window.disable_sticky_keys
window.sticky_keys? # => false
```

Both `enable_sticky_keys` and `disable_sticky_keys` must be called from within a `run` block definition.