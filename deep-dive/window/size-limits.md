# Size Limits

Most of the time, you'll want to constrain the size of a `Window` at creation using [*hints*](/deep-dive/window/creating-a-window/window-hints.md). If, however, you need to contextually constrain the min/max of a window's *size* after creation, CrystGLFW has a solution for you.

## `set_size_limits` and `size_limits=`

You can set an existing window's size limits using the `set_size_limits` method:

```crystal
window = Window.new(width: 640, height: 480)

# min_width is 100, min_height is 80, max_width is 1000, max_height is 800
window.set_size_limits(100, 80, 1000, 800)
```

You can use keyword arguments if you'd like:

```crystal
window = Window.new(width: 640, height: 480)

window.set_size_limits(min_width: 100, min_height: 80, max_width: 1000, max_height: 800)
```
Keyword arguments are particularly helpful when you only want to define a subset of the available limits:

```crystal
# only constrains the width
window.set_size_limits(min_width: 100, max_width: 1000)

# only constrains the height
window.set_size_limits(min_height: 80, max_height: 800)

# only enforces a maximum
window.set_size_limits(max_width: 1000, max_height: 800)
```

When constraining all four options (min_width, min_height, max_width, max_height), an alternate syntax is available in `size_limits=`:

```crystal
constraints = {min_width: 100, min_height: 80, max_width: 1000, max_height: 800}
window.size_limits = constraints
```

A `NamedTuple` passed to `size_limits=` *must* define constraints for all four options. Otherwise, use `set_size_limits`.

Both `set_size_limits` and `size_limits=` must be called from within a `run` block definition.