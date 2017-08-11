# Retrieving a Window's Corners

You have all that you need to retrieve the coordinates of each corner of a [`Window`](/deep-dive/window.md) object through `position` and `size`. But how about a shortcut? Why not, right?

## `corners`

The locations of a window's corners can be retrieved using the `corners` method:

```crystal
window = Window.new
window.corners[:bottom_right] # => {x: 1240, y: 880}
```
You can access individual corners using `:top_left`, `:top_right`, `:bottom_left`, `:bottom_right`:

```crystal
corners = window.corners
 
corners[:top_left]
corners[:top_right]
corners[:bottom_left]
corners[:bottom_right]
```
 
`corners` must be called from within a [`run`](/the-run-block.md) block definition. 
