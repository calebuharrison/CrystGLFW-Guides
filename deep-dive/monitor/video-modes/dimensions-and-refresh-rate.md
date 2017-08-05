# Width, Height, and Refresh Rate

You can retrieve the dimensions and the refresh rate of a `VideoMode` object.

## `width`, `height`, and `size`

If you'd like to know the width of a `VideoMode`, use the `width` method:

```crystal
video_mode = Monitor.primary.video_mode
video_mode.width # => 640
```
Of course, the height of the video mode is also available:

```crystal
video_mode.height # => 480
```
When, inevitably, you know that you'll need both, you can get them with one call to `size`:

```crystal
vm_size = video_mode.size
puts "width: #{vm_size[:width]}, height: #{vm_size[:height]}"
```
`size` returns a `NamedTuple(width: Int32, height: Int32)`, where `size[:width]` is the width of the video mode and `size[:height]` is the height of the video mode.

`width`, `height`, and `size` must be called from within a `run` block definition.

## `refresh_rate`

The refresh rate of a `VideoMode`, in Hz, is available via the `refresh_rate` method:

```crystal
rr = video_mode.refresh_rate
puts "The refresh rate is #{rr} Hz"
```

`refresh_rate` must be called from within a `run` block definition.