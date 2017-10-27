# Size and Refresh Rate

You can retrieve the dimensions and the refresh rate of a [`VideoMode`](/deep-dive/monitor/video-modes.md) object.

## `size`

If you'd like to know the dimensions of a [`VideoMode`](/deep-dive/monitor/video-modes.md), use the `size` method:

```crystal
vm_size = video_mode.size
puts "width: #{vm_size[:width]}, height: #{vm_size[:height]}"
```

`size` returns a `NamedTuple(width: Int32, height: Int32)`, where `size[:width]` is the width of the video mode and `size[:height]` is the height of the video mode.

`size` must be called from within a [`run`](/the-run-block.md) block definition.

## `refresh_rate`

The refresh rate of a [`VideoMode`](/deep-dive/monitor/video-modes.md), in Hz, is available via the `refresh_rate` method:

```crystal
rr = video_mode.refresh_rate
puts "The refresh rate is #{rr} Hz"
```

`refresh_rate` must be called from within a [`run`](/the-run-block.md) block definition.