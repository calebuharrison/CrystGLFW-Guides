# Gamma Exponents

You can set the [`GammaRamp`](/deep-dive/monitor/gamma-ramps.md) of a [`Monitor`](/deep-dive/monitor.md) using only an exponent that will be used to seed a new [`GammaRamp`](/deep-dive/monitor/gamma-ramps.md).

## `set_gamma` and `gamma=`

To set a monitor's gamma ramp using a seed `Number`, use the `set_gamma` method:

```crystal
monitor.set_gamma 3
```

Alternatively, you can use `gamma=` to achieve the same thing:

```crystal
monitor.gamma = 3
```

`set_gamma` and `gamma=` must be called from within a [`run`](/the-run-block.md) block definition.