# `CrystGLFW::Monitor::VideoMode`

A `CrystGLFW::Monitor::VideoMode` (or `VideoMode` for the purposes of this guide) represents a video mode, which is an attribute of `Monitor`. Objects of type `VideoMode` are created and destroyed internally.

## `video_mode`

The current video mode of a `Monitor` can be retrieved using the `video_mode` method:

```crystal
video_mode = monitor.video_mode # => CrystGLFW::Monitor::VideoMode
```

`video_mode` must be called from within a `run` block definition.

## `video_modes`

If you'd like to retrieve a list of all video modes supported by a `Monitor`, use the `video_modes` method:

```crystal
supported_video_modes = monitor.video_modes
puts supported_video_modes.size # prints the number of video modes supported by *monitor*
```

`video_modes` must be called from within a `run` block definition.