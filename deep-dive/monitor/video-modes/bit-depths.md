# Bit Depths
You can retrieve the bit depths of [`VideoMode`](/deep-dive/monitor/video-modes.md) color channels.

## `red_bits`, `green_bits`, and `blue_bits`
If you'd like to know the bit depth of the red channel of a [`VideoMode`](/deep-dive/monitor/video-modes.md), you can use the `red_bits` method:

```crystal
video_mode = Monitor.primary.video_mode
puts video_mode.red_bits # prints the bit depth of the red channel of *video_mode*
```

The same is true for the green channel and the blue channel:

```crystal
puts video_mode.green_bits # => 8
puts video_mode.blue_bits # => 8
```
`red_bits`, `green_bits`, and `blue_bits` must be called from within a [`run`](/the-run-block.md) block definition.