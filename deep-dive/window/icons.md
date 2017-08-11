# Icons

When a [`Window`](/deep-dive/window.md) is iconified, its *icon* may be displayed by the operating system at its discretion.

## `set_icon` and `icon=`

You can set the icon that you'd like the operating system to display using the `set_icon` method:

```crystal
image = Image.new(16, 16, pixels)
window = Window.new
window.set_icon(image)
```

It is recommended that the icon's size be 16x16, 32x32, or 48x48.

If you prefer, you can use `icon=` to achieve the same thing:

```crystal
image = Image.new(16, 16, pixels)
window = Window.new
window.icon = image
```

Both `set_icon` and `icon=` must be called from within a `run` block definition.