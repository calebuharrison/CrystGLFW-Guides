# Channels and Size

You can retrieve an array of numbers that represents the response of a color channel.

## `red`, `green`, and `blue`

If you want to get the response of the red channel of a [`GammaRamp`](/deep-dive/monitor/gamma-ramps.md), you can use the `red` method:

```crystal
gamma_ramp.red # => Array(UInt16)
```
The same is true for both the green and blue channels:

```crystal
gamma_ramp.green # => Array(UInt16)
gamma_ramp.blue # => Array(UInt16)
```

`red`, `green`, and `blue` must be called from within a [`run`](/the-run-block.md) block definition.

## `size`
You can use the `size` method to retrieve the size of the channel response arrays:

```crystal
gamma_ramp.size # => 1024
```

`size` must be called from within a [`run`](/the-run-block.md) block definition.
