# Full Screen Functionality

A [`Window`](/deep-dive/window.md) is said to be "full screened" if it is directly associated with a [`Monitor`](/deep-dive/monitor.md). If a [`Window`](/deep-dive/window.md) is not full screened, then it is "windowed."

## `full_screen?`

You can check to see if a [`Window`](/deep-dive/window.md) is full screened by calling the `full_screen?` method:

```crystal
window = Window.new
window.full_screen? # => false

monitor = Monitor.primary
window = Window.new(monitor: monitor)
window.full_screen? # => true
```

`full_screen?` must be called from within a [`run`](/the-run-block.md) block definition.

## `monitor`

If a [`Window`](/deep-dive/window.md) is full screened, you can retrieve the monitor on which it is displayed:

```crystal
if window.full_screen?
  window.monitor # => `CrystGLFW::Monitor`
end
```

If the window is not full screened when you attempt to retrieve its monitor, a `CrystGLFW::Error::NotFullScreen` will be raised.

`monitor` must be called from within a [`run`](/the-run-block.md) block definition.

## `set_monitor` and `monitor=`

To make a [`Window`](/deep-dive/window.md) full screened on a given [`Monitor`](/deep-dive/monitor.md), use the `set_monitor` method:

```crystal
window = Window.new
window.set_monitor(Monitor.primary)
```

The current [`VideoMode`](/deep-dive/monitor/video-modes.md) of the [`Monitor` ](/deep-dive/monitor.md)is used upon a [`Window`](/deep-dive/window.md) being full screened.

Alternatively, you can use `monitor=` to achieve the same thing:

```crystal
window = Window.new
window.monitor = Monitor.primary
```

Both `set_monitor` and `monitor=` must be called from within a [`run`](/the-run-block.md) block definition.

## `exit_full_screen`

To make a full screened [`Window`](/deep-dive/window.md) run in windowed mode, use the `exit_full_screen` method:

```crystal
window = Window.new(monitor: Monitor.primary)
window.exit_full_screen(100, 100, 640, 480)
```

`exit_full_screen` accepts the following arguments:
- *x*, the x-coordinate of the newly-windowed window. (Default: 100)
- *y*, the y-coordinate of the newly-windowed window. (Default: 100)
- *width*, the width of the newly-windowed window. (Default: 640)
- *height*, the height of the newly-windowed window. ( Default: 480)

```crystal
# location: (100, 100), size: 640x480
window.exit_full_screen(100, 100, 640, 480)

# location: (100, 100), size: 640x480
window.exit_full_screen

# location: (250, 50), size: 1024x576
window.exit_full_screen(250, 50, 1024, 576)
```

Of course, you can also use keyword arguments:

```crystal
# location: (250, 50), size: 1024x576
window.exit_full_screen(x: 250, y: 50, width: 1024, height: 576)
```

`exit_full_screen` must be called from within a [`run`](/the-run-block.md) block definition.


