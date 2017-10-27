# CrystGLFW::Window::Cursor

A `CrystGLFW::Window::Cursor` (or `Cursor`, for the purposes of this guide) represents the system cursor *with respect to* a given [`Window`](/deep-dive/window.md). Objects of type `Cursor` are always associated with a [`Window`](/deep-dive/window.md) and can only be created indirectly through a [`Window`](/deep-dive/window.md).

## `cursor`

You can create a `Cursor` by using the `cursor` method:

```crystal
window = Window.new
cursor = window.cursor # => CrystGLFW::Window::Cursor
```

Internally, if `window` does not yet have a cursor assigned to it, then one will be created and returned from the `cursor` method. If a `Cursor` has already been created for this `window`, then that `Cursor` will be returned.

If you wish to create a new `Cursor` for `window` with a given `Cursor::Shape`, you can pass it to the `cursor` method:

```crystal
window = Window.new
cursor = window.cursor(Window::Cursor::Shape::Arrow) # creates a cursor with the standard arrow shape

cursor = window.cursor(Window::Cursor::Shape::Crosshair) # creates a cursor with the crosshair shape

cursor = window.cursor # returns the previously created crosshair cursor.
```

The available shapes are:

- `Arrow`
- `IBeam`
- `Crosshair`
- `Hand`
- `HResize`
- `VResize`

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

The `cursor` method must be called from within a [`run`](/the-run-block.md) block definition.

## `remove_cursor`

You can remove a window's cursor without assigning a new cursor using the `remove_cursor` method:

```crystal
window = Window.new
cursor = window.cursor(Window::Cursor::Shape::Hand)

window.remove_cursor # removes the hand cursor, now the window has no cursor.
```

`remove_cursor` must be called from within a [`run`](/the-run-block.md) block definition.