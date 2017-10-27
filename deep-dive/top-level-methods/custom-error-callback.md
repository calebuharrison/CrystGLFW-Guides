# Custom Error Behavior

By default, CrystGLFW defines an error callback that raises an exception upon receiving an error event in the queue.

## `on_error`

Although not recommended, it is possible to define custom error behavior using `on_error`:

```crystal
CrystGLFW.on_error do |error_code|
  # your custom behavior here
end
```
`on_error` yields *error_code*, an `Int32`, that matches one of the GLFW error constants defined in the [GLFW3 specification](http://www.glfw.org/docs/latest/glfw3_8h.html#define-members). This `Int32` can be used to create a `CrystGLFW::Error`.  For reference, the default block definition looks like this:

```crystal
CrystGLFW.on_error do |error_code|
  CrystGLFW::Error.new(error_code).raise
end
```
It is the humble opinion of this guide that you not change this, and instead rescue exceptions where necessary. But hey - go crazy!

`on_error` can be invoked outside of a [`run`](/the-run-block.md) block definition.