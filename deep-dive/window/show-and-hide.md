# Show and Hide

A `Window` does not have to be visible at all times, and the `show` and `hide` methods allow for this behavior.

## `show`

To make a `Window` visible, use the `show` method:

```crystal
window = Window.new

# some code that results in the window being hidden

window.hide # makes the window visible again.
```

By default, windows are visible upon creation, though this can be configured via [hints](/deep-dive/window/creating-a-window/window-hints.md).

`show` must be called from within a `run` block definition.

## `hide`

To make a `Window` invisible, use the `hide` method:

```crystal
window = Window.new

window.hide # makes the window invisible.
```

`hide` must be called from within a `run` block definition.