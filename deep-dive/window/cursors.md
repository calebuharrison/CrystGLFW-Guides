# CrystGLFW::Window::Cursor

A `CrystGLFW::Window::Cursor` (or `Cursor`, for the purposes of this guide) represents the system cursor *with respect to* a given `Window`. Objects of type `Cursor` are always associated with a `Window` and can only be created indirectly through a `Window`.

## `cursor`

You can create a `Cursor` by using the `cursor` method:

```crystal
window = Window.new
cursor = window.cursor # => CrystGLFW::Window::Cursor
```

Internally, if `window` does not yet have a cursor assigned to it, then one will be created and returned from the `cursor` method. If a `Cursor` has already been created for this `window`, then that `Cursor` will be returned.

If you wish to create a new `Cursor` for `window` with a given shape, you can pass the shape's label to the `cursor` method:

```crystal
window = Window.new
cursor = window.cursor(:arrow_cursor) # creates a cursor with the standard arrow shape

cursor = window.cursor(:crosshair_cursor) # creates a cursor with the crosshair shape

cursor = window.cursor # returns the previously created crosshair cursor.
```

The following shapes are allowed:
- :arrow_cursor
- :hand_cursor
- :crosshair_cursor
- :vresize_cursor
- :hresize_cursor
- :ibeam_cursor

You can also create a `Cursor` with a custom appearance:

```crystal
window = Window.new
image = Window::Image.new(32, 32, pixels)
cursor = window.cursor(image, 0, 0) # creates a cursor that looks like *image*
```

When creating a custom cursor, the `cursor` method accepts the following arguments:

- *image*, the `Image` that the cursor should look like.
- *x*, the x-coordinate of the cursor's hotspot.
- *y*, the y-coordinate of the cursor's hotspot.

The `cursor` method must be called from within a `run` block definition.

## `remove_cursor`

You can remove a window's cursor without assigning a new cursor using the `remove_cursor` method:

```crystal
window = Window.new
cursor = window.cursor(:hand_cursor)

window.remove_cursor # removes the hand cursor, now the window has no cursor.
```

`remove_cursor` must be called from within a `run` block definition.