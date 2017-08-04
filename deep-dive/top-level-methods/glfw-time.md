# GLFW Time
GLFW has an internal timer that can be used in your application logic.

## `time`
As soon as CrystGLFW is initialized, it begins a timer. The value of this timer, in seconds, can be retrieved with the `time` method:

```crystal
current_time = CrystGLFW.time # => 0.13899576
```
`time` must be called after GLFW is initialized, and therefore must be called from within a `run` block definition.

## `set_time` and `time=`
You can manually set the timer to whatever value you'd like with the `set_time` method:

```crystal
CrystGLFW.set_time 3.5 # Sets the timer to 3 and a half seconds.
```

Alternatively, you can use `time=` to do the same thing:

```crystal
CrystGLFW.time = 3.5 # Sets the time to 3 and a half seconds.
```
`set_time` and `time=` must be called from within a `run` block definition.

## `timer_frequency` and `timer_value`
You can retrieve the frequency of the raw timer, in Hz, with `timer_frequency`:

```crystal
CrystGLFW.timer_frequency # => 1_000_000_000
```
Additionally, you can retrieve the current value of the raw timer, in 1 / `timer_frequency` seconds, with `timer_value`:

```crystal
CrystGLFW.timer_value # => 754_104_002_009_408
```
`timer_frequency` and `timer_value` must be called from within a `run` block definition.

