# The `contains?` Method

A `Window` is said to contain a location (a pair of coordinates) if that location is somewhere between a window's four corners.

## `contains?`

You can check to see if a window contains a location with the `contains?` method:

```crystal
# create a 500x500 window and set it in the top-left corner of the virtual screen
window = Window.new(width: 500, height: 500)
window.position = {x: 0, y: 0}

# (501, 501) is just outside the window
window.contains? 501, 501 # => false

# (250, 250) is smack in the middle of the window
window.contains? 250, 250 # => true

# (0,0) is the window's top-left corner
window.contains? 0, 0 # => true
```

As the example shows, `contains?` is inclusive, considering a window's corners and edges to be contained by the window.

The `contains?` method will also accept a `NamedTuple(x: Number, y: Number)` as an argument:

```crystal
# create a 500x500 window and set it in the top-left corner of the virtual screen
window = Window.new(width: 500, height: 500)
window.position = {x: 0, y: 0}

# (501, 501) is just outside the window
window.contains? {x: 501, y: 501} # => false

# (250, 250) is smack in the middle of the window
window.contains? {x: 250, y: 250} # => true
```

This allows you to use return values from other `CrystGLFW` methods as arguments without modification:

```crystal
window.contains? window.corners[:bottom_left] # => true
```

`contains?` must be called from within a `run` block definition.

