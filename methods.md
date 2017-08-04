# The Skeleton

Go ahead - I dare you. Just *try* to use CrystGLFW in a meaningful way without a main loop of some sort. I'll wait!

Obviously, at the heart of every CrystGLFW program is a main loop that draws a window (or multiple windows!) to a monitor (or multiple monitors!) while it processes some sort of input event (or multiple input events!) until it is closed by either the user or the program logic.

This guide cannot possibly predict all of the use cases you might have for CrystGLFW, but if this guide were a betting guide, it would probably put its money on your loop looking something like the one in this example:

```crystal
require "crystglfw"
include CrystGLFW

CrystGLFW.run do
  winston = Window.new width: 640, height: 480, title: "Winston the Window"
  
  until winston.should_close?
    CrystGLFW.poll_events
    winston.swap_buffers
  end
  
  winston.destroy
end
```

The above code is, with few exceptions, what pretty much every CrystGLFW application looks like. Let's break it down, starting with Winston the Window:

```crystal
winston = Window.new width: 640, height: 480, title: "Winston the Window" 
```
This line of code creates a new `CrystGLFW::Window` with a width of 640 (screen coordinates, not pixels), a height of 480 (also screen coordinates), and a title of "Winston The Window" and assigns it to a local variable called `winston`. Objects of type `CrystGLFW::Window` are first-class citizens in the world of CrystGLFW and you can find out more about them in the Deep Dive section of this guide. For now, all you need to know is that `winston` represents an actual GUI window that should be displayed on the screen at this point in runtime. Next up is our main loop:

```crystal
until winston.should_close?
  CrystGLFW.poll_events
  winston.swap_buffers
end
```
This loop continues to run until `winston` is *marked for closing* in some way by the operating system, user input, or application logic. This occurs most commonly by the user "ex-ing out" of the window. Until then, CrystGLFW will poll its internal event queue for any events that need to be processed before swapping its buffers to redraw itself.

Once `winston.should_close?` returns `true`, the loop condition will be broken and the program will have no choice but to mercilessly destroy `winston`:

```crystal
winston.destroy
```
The `CrystGLFW::Window#destroy` method will destroy the underlying GLFW window that is wrapped by CrystGLFW, rendering the local variable `winston` completely unusable. Any further attempt to use `winston` or access any of its attributes will result in a raised exception.

Technically, in this particular example, calling `destroy` on `winston` is unnecessary, since the `run` block will clean up whatever is left when it reaches its end. If, however, you want to close a window long before you want to terminate GLFW as a whole, then you will want to use `CrystGLFW::Window#destroy`.

