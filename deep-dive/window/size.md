# Retrieving and Setting a Window's Size

This *size* of a `Window` is synonymous with its dimensions - a window's *size* describes both its width and its height in screen coordinates.

## `size`

You can retrieve a window's *size* using the aptly-named `size` method:

```crystal
window = Window.new(width: 600, height: 400)
window.size # => {width: 600, height: 400}
```
The returned *size* is of type `NamedTuple(width: Int32, height: Int32)`, so the individual *width* and *height* values can be accessed using `:width` and `:height`, respectively:

```crystal
window.size[:width] # => 600
window.size[:height # => 400
```

`size` must be called from within a `run` block definition.

## `set_size` and `size=`

If you wish to manually assign a `Window` a new size, you can do so using the `set_size` method:

```crystal
window = Window.new(width: 600, height: 400)
window.size # => {width: 600, height: 400}

window.set_size(640, 480)
window.size # => {width: 640, height: 480}
```

Of course, you can also use keyword arguments:

```crystal
window.set_size(width: 640, height: 480)
window.size # => {width: 640, height: 480}
```

`set_size` receives two distinct arguments:
- *width*, the window's new width.
- *height*, the window's new height.

Both arguments are of type `Int32`.

Alternatively, you can set the *size* of a `Window` using the `size=` method:

```crystal
window = Window.new(width: 600, height: 400)
window.size # => {width: 600, height: 400}

window.size = {width: 640, height: 480}
window.size # => {width: 640, height: 480}
```

`size` receives only one argument:
- *s*, the desired *size* of the window.

*s* is of type `NamedTuple(width: Int32, height: Int32`

Both `set_size` and `size=` must be called from within a `run` block definition.