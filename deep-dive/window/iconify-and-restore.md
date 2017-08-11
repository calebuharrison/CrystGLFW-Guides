# Iconify and Restore

A [`Window`](/deep-dive/window.md) is said to be "iconified" if it has been minimized, and a [`Window`](/deep-dive/window.md) is said to be "restored" if it has been de-minimized.

## `iconify`

To manually minimize a [`Window`](/deep-dive/window.md), you can use the `iconify` method:

```crystal
window = Window.new
window.iconify # minimizes the window
```

If the [`Window`](/deep-dive/window.md) is in full screen mode when `iconify` is called, the [`Monitor`](/deep-dive/monitor.md) will have its original resolution restored until the window is restored.

`iconify` must be called from within a [`run`](/the-run-block.md) block definition.

## `restore`

To manually restore a [`Window`](/deep-dive/window.md) from iconification or maximization, you can use the `restore` method:

```crystal
window = Window.new
window.iconify # minimizes the window

window.restore # restores the window
```

`restore` must be called from within a [`run`](/the-run-block.md) block definition.