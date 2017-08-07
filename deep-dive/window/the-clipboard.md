# The Clipboard

The contents of the system clipboard can be accessed directly from a `Window` in your application logic.

## `clipboard`

To retrieve the current contents of the system clipboard as a `String`, use the `clipboard` method:

```crystal
window = Window.new
puts window.clipboard # prints the contents of the system clipboard to the screen.
```

If the clipboard is empty or not UTF-8 encoded, a `CrystGLFW::Error::FormatUnavailable` will be raised.

`clipboard` must be called from within a `run` block definition.

## `set_clipboard`

To manually set the contents of the system clipboard, use the `set_clipboard` method:

```crystal
window = Window.new
window.set_clipboard("Hello World!")

window.clipboard # => "Hello World!"
```

Alternatively, you can use the `clipboard=` method to achieve the same thing:

```crystal
window = Window.new
window.clipboard = "Hello World!"

window.clipboard # => "Hello World!"
```

Both `clipboard` and `clipboard=` must be called from within a `run` block definition.