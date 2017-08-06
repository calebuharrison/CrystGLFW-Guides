# Aspect Ratio

You can set the aspect ratio of a `Window` after creation.

## `set_aspect_ratio` and `aspect_ratio=`

If you'd like to manually set a window's aspect ratio, you can use the `set_aspect_ratio` method:

```crystal
window = Window.new
window.set_aspect_ratio(16, 9)
```

You can optionally choose to use keyword arguments:

```crystal
window.set_aspect_ratio(numerator: 16, denominator: 9)
```

Setting the aspect ratio of a `Window` will only take effect if the window is running in windowed mode (i.e. the window is not full screened). The new aspect ratio is immediately applied and is likely to cause the window to resize itself.

An alternative syntax is available in the form of `aspect_ratio=`:

```crystal
window.aspect_ratio = {numerator: 4, denominator: 3}
```

Both `set_aspect_ratio` and `aspect_ratio=` must be called from within a `run` block definition.
