# `CrystGLFW.run`

Under the hood, GLFW must be manually initialized and terminated in order for it to work properly. CrystGLFW does most of the heavy lifting for you, asking only that you define all of your CrystGLFW functionality inside of a block given to the `run` method:

```crystal
require "crystglfw"

CrystGLFW.run do
  # your code here
end
```
The `run` method will initialize the underlying GLFW library and yield to the code that you write in the block before safely terminating. No need to worry about memory leaks and such - `run` will take care of the memory management for you.

As you peruse the [docs](https://calebuharrison.github.io/CrystGLFW), you'll notice that almost all of the methods provided by CrystGLFW are marked with a note that warns against using them outside of a `run` block definition. Indeed, only a small handful (a palmful?) of methods can be used outside of `run`, so tread lightly until you find yourself in the safe, comfortable embrace of a `run` block.

```crystal
require "crystglfw"

# Nope! Error! What were you thinking!?
window = CrystGLFW::Window.new(title: "My Failed Window")

CrystGLFW.run do

  # That's more like it! Thanks, `run`!
  window = CrystGLFW::Window.new(title: "My Much More Successful Window")
  
  # do cool stuff with your window here
  until window.should_close?
    CrystGLFW.wait_events
    window.swap_buffers
  end
  
  # she had a good life, time to put her down.
  window.destroy
end
```
Of course, if you actually compile and run the code above, your poor program won't make it to the happy part - the part where that successful window gets created and lives a happy life, then dies comfortably surrounded by friends and family. No, if you try to run this code, CrystGLFW will toss you a `CrystGLFW::Error::NotInitialized` exception at runtime by default. More on that later!

