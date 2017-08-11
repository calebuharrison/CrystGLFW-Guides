# `CrystGLFW::Monitor`

A `CrystGLFW::Monitor` (or just `Monitor` for the purposes of this guide) represents a physical display connected to the system running your application. Since monitors are physical objects, they cannot be created through CrystGLFW directly - creation and destruction of `Monitor` objects are handled internally.

## `primary`

The `primary` class method returns a `Monitor` object that represents the system's primary or "preferred" monitor. This monitor is usually denoted by the presence of global UI elements such as menu and task bars.

```crystal
monitor = CrystGLFW::Monitor.primary
```

`primary` must be called from within a `run` block definition.

## `all`

The `all` class method returns an array of `Monitor` objects, representing all of the displays currently connected to the system.

```crystal
monitors = CrystGLFW::Monitor.all
puts monitors.size # prints the number of currently connected monitors
```

`all` must be called from within a `run` block definition.

## `on_toggle_connection`

`on_toggle_connection` defines the desired callback behavior when a `Monitor` is either connected or disconnected.

```crystal
CrystGLFW::Monitor.on_toggle_connection do |event|
  if event.connected?
    puts "A monitor was just connected: #{event.monitor.name}"
  else
    puts "A monitor was just disconnected."
  end
end
```
`on_toggle_connection` yields a [`CrystGLFW::Event::MonitorToggleConnection`](/deep-dive/events/monitortoggleconnection.md) to the block, and can be called from outside of a `run` block definition.