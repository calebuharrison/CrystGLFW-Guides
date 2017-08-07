# Destroying a Window

To close a `Window`, it must be destroyed using the `destroy` method:

```crystal
window.destroy
```

When a `Window` is destroyed, the `GLFWwindow` pointer that it encapsulates become obsolete. If you attempt to use a `Window` for some purpose after it has been destroyed, either a `CrystGLFW::Error::Any` will be raised or some undefined behavior will occur. For this reason, never use a destroyed window! Make sure that `destroy` is the last method used on a `Window` object in your application logic and you'll be golden.

`destroy` must be called from within a `run` block definition.