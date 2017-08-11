# Show and Hide

A [`Window`](/deep-dive/window.md) does not have to be visible at all times, and the `show` and `hide` methods allow for this behavior.

## `show`

To make a [`Window`](/deep-dive/window.md) visible, use the `show` method:

```crystal
window = Window.new

# some code that results in the window being hidden

window.show # makes the window visible again.
```

By default, windows are visible upon creation, though this can be configured via [hints](/deep-dive/window/creating-a-window/window-hints.md).

`show` must be called from within a [`run`](/the-run-block.md) block definition.

## `hide`

To make a [`Window`](/deep-dive/window.md) invisible, use the `hide` method:

```crystal
window = Window.new

window.hide # makes the window invisible.
```

`hide` must be called from within a [`run`](/the-run-block.md) block definition.