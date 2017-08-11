# Retrieving Position, Physical Size, and Name

[`Monitor`](/deep-dive/monitor.md) has very few public attributes, but here they are! For each of the entries below, assume:
```crystal
monitor = CrystGLFW::Monitor.primary
```

## `position`
You can retrieve the position of a [`Monitor`](/deep-dive/monitor.md), in screen coordinates, using the `position` method:

```crystal
monitor_pos = monitor.position
puts "(#{monitor_pos[:x]}, #{monitor_pos[:y]})" # => "(0, 0)"
```
`position` returns a `NamedTuple(x: Int32, y: Int32)`, where `position[:x]` represents the x-coordinate of the monitor's position and `position[:y]` represents the y-coordinate of the monitor's position. The position given is the location, in screen coordinates, of the monitor's top-left corner, relative to the virtual screen.

`position` must be called from within a [`run`](/the-run-block.md) block definition.

## `physical_size`
GLFW can estimate the physical dimensions of a monitor, measured in millimeters:

```crystal
dimensions = monitor.physical_size
puts "The monitor is approximately #{dimensions[:width]} mm wide."
puts "And it is approximately #{dimensions[:height]} mm tall."
```

`physical_size` returns a `NamedTuple(width: Int32, height: Int32)`, where `physical_size[:width]` returns the physical width of the monitor in millimeters and `physical_size[:height]` returns the physical height of the monitor in millimeters.

`physical_size` must be called from within a [`run`](/the-run-block.md) block definition.

## `name`
Each [`Monitor`](/deep-dive/monitor.md) has a model name given to it by its manufacturer, which can be retrieved with `name`:

```crystal
monitor_name = monitor.name
puts "The monitor's name is #{monitor_name}."
```

`name` returns a `String` that contains the monitor's given name.

`name` must be called from within a [`run`](/the-run-block.md) block definition.

