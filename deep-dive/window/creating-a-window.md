# Creating a Window

You can create a `CrystGLFW::Window` with the `new` method:

```crystal
window = CrystGLFW::Window.new
window # => CrystGLFW::Window
```

Using `new` to create a `Window` will cause an actual GUI window to be created on the machine - this window contains the OpenGL or OpenGL ES context that can be used for drawing.

`new` accepts the following arguments, all of which are optional:
- *width*, the starting width of the window, in screen coordinates.
- *height*, the starting height of the window, in screen coordinates.
- *title*, the title of the window, commonly displayed at the top of its frame.
- *monitor*, the `Monitor` to use for full screen mode.
- *sharing_window*, the `Window` with which the new window should share resources.
- *hints*, a `Hash` of desired constraints that will be placed on the created window.

Let's examine each of these arguments in detail.

## *width* and *height*

The starting *width* and *height* of a window can be configured using the *width* and *height* arguments, respectively:

```crystal
# create a window with initial dimensions of 1024x576.
window = CrystGLFW::Window.new(width: 1024, height: 576)

# create a window with initial dimensions of 800x800
window = CrystGLFW::Window.new(width: 800, height: 800)
```

Both arguments have a default values:
- *width* defaults to 640
- *height* defaults to 480

Each of these calls to `new` creates a 640x480 window:

```crystal
window = Window.new(width: 640, height: 480)

window = Window.new(width: 640)

window = Window.new(height: 480)

window = Window.new
```
Remember: these dimensions are *screen coordinates*, not pixels.

## *title*

You can set the window's starting title by using the *title* argument:

```crystal
# create a window titled "test window"
window = Window.new(title: "test window")

# create a window titled "Winston the Window"
window = Window.new(title: "Winston the Window")
```
The default value of *title* is an empty `String`. This won't throw an error, but it's also not a great window title. Give your window some love - let it have a title!

## *monitor*

If you'd like for the new window to immediately begin running in full screen mode, you can use the *monitor* argument to indicate which monitor should be used:

```crystal
primary_monitor = Monitor.primary
window = Window.new(monitor: primary_monitor)
```
By default, windows run in windowed mode rather than full screen. Providing a `Monitor` to the *monitor* argument tells CrystGLFW that you'd like to run in full screen mode. Because of this, if *width* and *height* are given alongside *monitor*, then *width* and *height* will be ignored:

```crystal
primary_monitor = Monitor.primary

# still creates a full screen window on the primary monitor.
window = Window.new(width: 1024, height: 576, monitor: primary_monitor)
```

## *sharing_window*
If the new window needs to share its context objects with another window's context, you can use the *sharing_window* argument:

```crystal
winston = Window.new
wilfred = Window.new(sharing_window: winston)
```

## *hints*
