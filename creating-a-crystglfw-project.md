# Bare Essentials

Let's get right down to it - what are the bare essentials required for using CrystGLFW? We'll need to start by making sure we've got GLFW3 on our system.

On MacOS, this is dead simple thanks to homebrew:

```sh
brew install glfw3
```

## Dependencies

Open up your Crystal project's shard.yml and add this:

```yaml
dependencies:
  crystglfw:
    github: calebuharrison/CrystGLFW
    branch: master
```
Now install dependencies from your project's root:
```sh
shards install
```

## Require and Include

Navigate to the Crystal file in your project that will use CrystGLFW and require it:

```crystal
require "crystglfw"
```
This makes all of CrystGLFW accessible in your file. You can make sure things are working by asking CrystGLFW for the version of the underlying GLFW installation.

```crystal
require "crystglfw"

version = CrystGLFW.version # => {major: 3, minor: 2, rev: 1}
puts "#{version[:major]}.#{version[:minor}.#{version[:rev]}" # => "3.2.1"
```

Remember to compile and run your project from the project's root. Otherwise, the compiler may complain about being unable to locate CrystGLFW.

If everything is working, then you can consider including the CrystGLFW module in addition to simply requiring its containing file:

```crystal
require "crystglfw"
include CrystGLFW
```

This allows you to optionally omit the CrystGLFW namespace when referring to a CrystGLFW type:

```crystal
# without include
require "crystglfw"
CrystGLFW::Window # => CrystGLFW::Window
Window # => error, undefined constant


# with include
require "crystglfw"
include CrystGLFW
CrystGLFW::Window # => CrystGLFW::Window
Window # => CrystGLFW::Window
```
Including the CrystGLFW module can make your code cleaner and much less of a drag to write, but it can also increase the odds of clashing with another type's name in your project. The choice is up to you!