# `CrystGLFW::Window`

A `CrystGLFW::Window` (or `Window`, for the purposes of this guide) represents a combined GUI window and its associated OpenGL or OpenGL ES context. Astonishingly, it only has one class method:

## `current`

The `current` class method returns the `Window` object whose context is current:

```crystal
current_window = CrystGLFW::Window.current
current_window # => CrystGLFW::Window
```
If there is no current context, then a `CrystGLFW::Error::NoCurrentContext` is raised.

`current` must be called from within a `run` block definition.