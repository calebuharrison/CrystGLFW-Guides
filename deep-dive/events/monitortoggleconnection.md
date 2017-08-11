# `CrystGLFW::Event::MonitorToggleConnection`

A `CrystGLFW::Event::MonitorToggleConnection` is generated when a [`Monitor`](/deep-dive/monitor.md) is either connected or disconnected. It is yielded to the block defined by [`Monitor#on_toggle_connection`](/deep-dive/monitor.md).

```crystal
CrystGLFW::Monitor.on_toggle_connection do |event|
  if event.connected?
    puts "A monitor was just connected: #{event.monitor.name}"
  else
    puts "A monitor was just disconnected."
  end
end
```

## `monitor`

You can retrieve the monitor that was connected/disconnected using the `monitor` method:

```crystal
event.monitor # => CrystGLFW::Monitor
```

## `connected?`

You can use the `connected?` method to determine if the [`Monitor`](/deep-dive/monitor.md) was connected or disconnected:

```crystal
event.connected? # => Bool
```

`connected?` returns `true` if the [`Monitor`](/deep-dive/monitor.md) was connected, and returns `false` if it was disconnected.



