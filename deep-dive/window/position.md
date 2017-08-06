# Retrieving and Setting a Window's Position

The *position* of a `Window` is a set of screen coordinates that indicate the location of the GUI window's top-left corner relative to the virtual screen.

## `position`

You can retrieve a window's current position using the `position` method:

```crystal
window = Window.new
pos = window.position
pos[:x] # the x-coordinate of the position
pos[:y] # the y-coordinate of the position
```

The returned *position* is a `NamedTuple(x: Int32, y: Int32)`.

`position` must be called from within a `run` block definition.

## `set_position` and `position=`

A window's position can be set manually in your application's logic using the `set_position` method:

```crystal
window = Window.new
window.set_position(100, 100) # sets the window's top-left corner at (100, 100)
```

Of course, you can also use named arguments:

```crystal
window.set_position(x: 100, y: 100)
```

`set_position` accepts two distinct arguments:

- *x*, the x-coordinate of the desired position.
- *y*, the y-coordinate of the desired position.

Both arguments are of type `Int32`.

Alternatively, you can set a window's position with the `position=` method to achieve the same thing:

```crystal
window.position = {x: 100, y: 100} # sets the window's top-left corner at (100, 100)
```

`position=` accepts only one argument:

- *pos*, the desired location of the window's top-left corner.

*pos* is of type `NamedTuple(x: Int32, y: Int32)`

Both `set_position` and `position=` must be called from within a `run` block definition.