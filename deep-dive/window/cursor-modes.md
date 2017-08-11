# Cursor Modes

GLFW "Cursor Modes" alter the functionality and visibility of a window's associated [`Cursor`](/deep-dive/window/cursors.md). These modes persist beyond the lifetime of an individual [`Cursor`](/deep-dive/window/cursors.md), so they are accessed/modified at the [`Window`](/deep-dive/window.md) level.

## `cursor_normal?` and `normalize_cursor`

The "normal" cursor mode makes a window's [`Cursor`](/deep-dive/window/cursors.md) visible and behave traditionally. By default, windows are in normal cursor mode. You can check to see if a [`Window`](/deep-dive/window.md) is in normal cursor mode using the `cursor_normal?` method:

```crystal
window.cursor_normal?
```

`cursor_normal?` returns `true` if `window` is in normal cursor mode, and returns `false` otherwise.

You can set a window's cursor mode to normal using the `normalize_cursor` method:

```crystal
window.normalize_cursor
```

Both `cursor_normal?` and `normalize_cursor` must be called from within a [`run`](/the-run-block.md) block definition.

## `cursor_hidden?` and `hide_cursor`

The "hidden" cursor mode makes a window's [`Cursor`](/deep-dive/window/cursors.md) invisible, but does not restrict the [`Cursor`](/deep-dive/window/cursors.md) from leaving the window. You can check to see if a [`Window`](/deep-dive/window.md) is in hidden cursor mode using the `cursor_hidden?` method:

```crystal
window.cursor_hidden?
```

`cursor_hidden?` returns `true` if `window` is in hidden cursor mode, and returns `false` otherwise.

You can set a window's cursor mode to hidden using the `hide_cursor` method:

```crystal
window.hide_cursor
```

Both `cursor_hidden?` and `hide_cursor` must be called from within a [`run`](/the-run-block.md) block definition.

## `cursor_disabled?` and `disable_cursor`

The "disabled" cursor mode makes a window's [`Cursor`](/deep-dive/window/cursors.md) invisible and removes all restrictions/boundaries for the cursor's movement. You can check to see if a [`Window`](/deep-dive/window.md) is in disabled cursor mode using the `cursor_disabled?` method:

```crystal
window.cursor_disabled?
```

`cursor_disabled?` returns `true` if `window` is in disabled cursor mode, and returns `false` otherwise.

You can set a window's cursor mode to disabled using the `disable_cursor` method:

```crystal
window.disable_cursor
```

Both `cursor_disabled?` and `disable_cursor` must be called from within a [`run`](/the-run-block.md) block definition.
