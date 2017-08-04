# GLFW Version
CrystGLFW exposes two methods for getting the version of the underlying GLFW binary. Both can safely be called outside of a `run` block definition.

## `version`

If you want to know what version of GLFW is being used under the hood of GLFW, you can use the `version` method:

```crystal
glfw_version = CrystGLFW.version # => {major: 3, minor: 2, rev: 1}
puts "The revision version number of GLFW is #{glfw_version[:rev]}"
```

`version` returns a `NamedTuple(major: Int32, minor: Int32, rev: Int32)`. Each version number is pulled from the underlying GLFW installation on your machine. If part of your application logic needs to use the GLFW version number, use this method to retrieve it.

`version` is safe to use outside of a `run` block definition.

## `version_string`
The GLFW API exposes a compile-time generated string that describes the version, platform, compiler, and any platform-specific compile-time configurations:

```crystal
puts CrystGLFW.version_string # => "3.2.1 Cocoa NSGL chdir menubar retina dynamic"
```
This method is useful for debugging, but shouldn't be used for your application logic. Use `version` instead.

`version_string` is safe to use outside of a run block definition.

