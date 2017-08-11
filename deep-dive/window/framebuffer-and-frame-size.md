# Framebuffer and Frame Size

## `framebuffer_size`

To retrieve the window's *framebuffer_size*, use the `framebuffer_size` method:

```crystal
window = Window.new(width: 640, height: 480)
window.framebuffer_size # => {width: 1280, height: 960}
```

Unlike most CrystGLFW *size* representations, **the returned framebuffer_size is in pixels, not screen coordinates**.

`framebuffer_size` must be called from within a [`run`](/the-run-block.md) block definition.

## `frame_size`

You can retrieve the size of each edge of the window's frame, including its title bar (if present) with the `frame_size` method:

```crystal
frame_size = window.frame_size
frame_size[:top] # => the "height" of the window's top frame edge
```

All four edges of the frame can be accessed: `:top`, `:right`, `:bottom`, and `:left`.

Note that unlike `framebuffer_size`, each edge's size is given in screen coordinates, not pixels.

`frame_size` must be called from within a [`run`](/the-run-block.md) block definition.