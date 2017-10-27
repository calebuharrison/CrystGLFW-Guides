# Cursor Modes

GLFW "Cursor Modes" alter the functionality and visibility of a window's associated [`Cursor`](/deep-dive/window/cursors.md).

## `normal?` and `normalize`

The "normal" cursor mode makes a [`Cursor`](/deep-dive/window/cursors.md) visible and makes it behave traditionally. By default, cursors are in normal mode. You can check to see if a [`Cursor`](/deep-dive/window/cursors.md) is in normal mode using the `normal?` method:

```crystal
cursor.normal?
```

`normal?` returns `true` if `cursor` is in normal mode, and returns `false` otherwise.

You can set a cursor's mode to normal using the `normalize` method:

```crystal
window.normalize
```

Both `normal?` and `normalize` must be called from within a [`run`](/the-run-block.md) block definition.

## `hidden?` and `hide`

The "hidden" cursor mode makes a [`Cursor`](/deep-dive/window/cursors.md) invisible, but does not restrict the [`Cursor`](/deep-dive/window/cursors.md) from leaving the window. You can check to see if a [`Cursor`](/deep-dive/window/cursors.md) is in hidden mode using the `hidden?` method:

```crystal
cursor.hidden?
```

`hidden?` returns `true` if `cursor` is in hidden mode, and returns `false` otherwise.

You can set a cursor's mode to hidden using the `hide` method:

```crystal
cursor.hide
```

Both `hidden?` and `hide` must be called from within a [`run`](/the-run-block.md) block definition.

## `disabled?` and `disable`

The "disabled" cursor mode makes a [`Cursor`](/deep-dive/window/cursors.md) invisible and removes all restrictions/boundaries for the cursor's movement. You can check to see if a [`Cursor`](/deep-dive/window/cursors.md) is in disabled mode using the `disabled?` method:

```crystal
cursor.disabled?
```

`disabled?` returns `true` if `cursor` is in disabled mode, and returns `false` otherwise.

You can set a cursor's mode to disabled using the `disable` method:

```crystal
cursor.disable
```

Both `disabled?` and `disable` must be called from within a [`run`](/the-run-block.md) block definition.
