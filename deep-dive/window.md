# `CrystGLFW::Window`

A `CrystGLFW::Window` (or `Window`, for the purposes of this guide) represents a combined GUI window and its associated OpenGL or OpenGL ES context. Astonishingly, it only has one class method:

## `current`

The `current` class method returns the `Window` object whose context is current:

```crystal
current_window = CrystGLFW::Window.current
current_window # => CrystGLFW::Window
```
If there is no current context, then an exception is raised by  `Error::NoCurrentContext`.

`current` must be called from within a [`run`](/the-run-block.md) block definition.