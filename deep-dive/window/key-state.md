# Key State

Each individual [`Window`](/deep-dive/window.md) keeps a record of each key's state - this state can either be "press" or "release." Each window maintains its own record because windows only receive information from the keyboard when they have input focus. Therefore multiple windows can have different interpretations of the full keyboard's state.

## `key_pressed?`

You can find out whether or not a specific [`Window`](/deep-dive/window.md) thinks a [`Key`](/deep-dive/keys.md) is currently pressed or released using the `key_pressed?` method:

```crystal
key = event.key # => CrystGLFW::Key
window.key_pressed?(key) # => Bool
```

`key_pressed?` returns `true` if the [`Window`](/deep-dive/window.md) thinks that the [`Key`](/deep-dive/keys.md) is currently pressed, and returns `false` if the [`Window`](/deep-dive/window.md) thinks that the [`Key`](/deep-dive/keys.md) is currently released. The return value of this method *is* affected by [sticky keys](/deep-dive/window/sticky-keys.md).