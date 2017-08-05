# Bit Depths
You can retrieve the bit depths of `VideoMode` color channels.

## `red_bits`, `green_bits`, and `blue_bits`
If you'd like to know the bit depth of the red channel of a `VideoMode`, you can use the `red_bits` method:

```crystal
video_mode = Monitor.primary.video_mode
puts video_mode.red_bits # prints the bit depth of the red channel of *video_mode*
```

The same is true for the green channel and the blue channel:

```crystal
puts video_mode.green_bits # => 8
puts video_mode.blue_bits # => 8
```
`red_bits`, `green_bits`, and `blue_bits` must be called from within a `run` block definition.

## `channel_bits`
Being able to retrieve the bit depths of individual color channels is great - but sometimes you just want them all. Enter `channel_bits`:

```crystal
video_mode = Monitor.primary.video_mode
channels = video_mode.channel_bits
puts channels[:red] #   => 8
puts channels[:green] # => 8
puts channels[:blue] #  => 8
```
`channel_bits` must be called from within a `run` block definition.