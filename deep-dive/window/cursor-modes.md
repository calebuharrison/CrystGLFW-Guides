# Cursor Modes

GLFW "Cursor Modes" alter the functionality and visibility of a window's associated `Cursor`. These modes persist beyond the lifetime of an individual `Cursor`, so they are accessed/modified at the `Window` level.

## `cursor_normal?` and `normalize_cursor`

The "normal" cursor mode makes a window's `Cursor` visible and behave traditionally. By default, windows are in normal cursor mode. You can check to see if a `Window` is in normal cursor mode using the `cursor_normal?` method:

```crystal
window.cursor_normal?
```

`cursor_normal?` returns `true` if `window` is in normal cursor mode, and returns `false` otherwise.

You can set a window's cursor mode to normal using the `normalize_cursor` method:

```crystal
window.normalize_cursor
```

Both `cursor_normal?` and `normalize_cursor` must be called from within a `run` block definition.

## `cursor_hidden?` and `hide_cursor`

The "hidden" cursor mode makes a window's `Cursor` invisible, but does not restrict the `Cursor` from leaving the window. You can check to see if a `Window` is in hidden cursor mode using the `cursor_hidden?` method:

```crystal
window.cursor_hidden?
```

`cursor_hidden?` returns `true` if `window` is in hidden cursor mode, and returns `false` otherwise.

You can set a window's cursor mode to hidden using the `hide_cursor` method:

```crystal
window.hide_cursor
```

Both `cursor_hidden?` and `hide_cursor` must be called from within a `run` block definition.

## `cursor_disabled?` and `disable_cursor`

The "disabled" cursor mode makes a window's `Cursor` invisible and removes all restrictions/boundaries for the cursor's movement. You can check to see if a `Window` is in disabled cursor mode using the `cursor_disabled?` method:

```crystal
window.cursor_disabled?
```

`cursor_disabled?` returns `true` if `window` is in disabled cursor mode, and returns `false` otherwise.

You can set a window's cursor mode to disabled using the `disable_cursor` method:

```crystal
window.disable_cursor
```

Both `cursor_disabled?` and `disable_cursor` must be called from within a `run` block definition.
