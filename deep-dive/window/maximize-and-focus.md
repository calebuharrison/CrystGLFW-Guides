# Maximize and Focus

## `maximize`

To maximize a `Window`, use the `maximize` method:

```crystal
window = Window.new
window.maximize # maximize the window
```

Maximization can be reversed with the `restore` method.

`maximize` must be called from within a `run` block definition.

## `focus`

To bring a `Window` to the user's attention and receive input, use the `focus` method:

```crystal
window = Window.new
window.focus
```

`focus` must be called from within a `run` block definition.

