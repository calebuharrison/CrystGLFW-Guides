# Maximize and Focus

## `maximize`

To maximize a [`Window`](/deep-dive/window.md), use the `maximize` method:

```crystal
window = Window.new
window.maximize # maximize the window
```

Maximization can be reversed with the `restore` method.

`maximize` must be called from within a [`run`](/the-run-block.md) block definition.

## `focus`

To bring a [`Window`](/deep-dive/window.md) to the user's attention and receive input, use the `focus` method:

```crystal
window = Window.new
window.focus
```

`focus` must be called from within a [`run`](/the-run-block.md) block definition.

