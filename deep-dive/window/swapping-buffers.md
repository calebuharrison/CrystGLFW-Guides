# Swapping Buffers

A [`Window`](/deep-dive/window.md) is double-buffered, which is to say that it has two different canvases that can be drawn/displayed. When one of these canvases is being drawn to, the other is being displayed to the user. When draw calls to a window's back buffer have been completed, the window needs to swap its buffers so that the image can be displayed.

## `swap_buffers`

You can swap the front and back buffers of a [`Window`](/deep-dive/window.md) using the `swap_buffers` method:

```crystal
window.swap_buffers
```

You'll most commonly use this method at the end of your main loop to swap buffers upon each iteration. For an example of this, see [the skeleton](/the-skeleton.md).

`swap_buffers` must be called from within a [`run`](/the-run-block.md) block definition.