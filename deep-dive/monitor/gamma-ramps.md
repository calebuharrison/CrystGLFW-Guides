# `CrystGLFW::Monitor::GammaRamp`

A `CrystGLFW::Monitor::GammaRamp` (or `GammaRamp`, for the purposes of this guide) represents a gamma ramp belonging to a [`Monitor`](/deep-dive/monitor.md). Objects of type `GammaRamp` are created and destroyed internally.

## `gamma_ramp`
The current gamma ramp of a [`Monitor`](/deep-dive/monitor.md) can be retrieved using the `gamma_ramp` method:

```crystal
gamma_ramp = CrystGLFW::Monitor.primary.gamma_ramp # => CrystGLFW::Monitor::GammaRamp
```
`gamma_ramp` must be called from within a `run` block definition.

## `set_gamma_ramp` and `gamma_ramp=`
If you'd like to manually set a gamma ramp for a [`Monitor`](/deep-dive/monitor.md), you can do so with `set_gamma_ramp`:

```crystal
monitors = CrystGLFW::Monitor.all
if monitors.size > 1
  monitors.first.set_gamma_ramp(monitors.last.gamma_ramp)
end
```
Alternatively, you can use `gamma_ramp=` to achieve the same thing:

```crystal
monitors = CrystGLFW::Monitor.all
if monitors.size > 1
  monitors.first.gamma_ramp = monitors.last.gamma_ramp
end
```

`set_gamma_ramp` and `gamma_ramp=` must be called from within a [`run`](/the-run-block.md) block definition.