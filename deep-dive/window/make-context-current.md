# Make Context Current

A [`Window`](/deep-dive/window.md) is not simply a GUI window on the screen - it is also an OpenGL or OpenGL ES context. OpenGL and OpenGL ES can juggle multiple contexts, but only one context can be targeted at once. This context is the "current context."

## `make_context_current`

You can declare which context should be the current context by using the `make_current_context` method:

```crystal
winston = Window.new
wilfred = Window.new

winston.make_context_current
```

In the above example, even though both `winston` and `wilfred` are valid OpenGL contexts, `winston` becomes the current context and will be the `Window` to receive draw calls until `wilfred` demands to be the current context.

`make_context_current` must be called from within a [`run`](/the-run-block.md) block definition.