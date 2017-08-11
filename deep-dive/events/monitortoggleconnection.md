# `CrystGLFW::Event::MonitorToggleConnection`

A `CrystGLFW::Event::MonitorToggleConnection` is generated when a `Monitor` is either connected or disconnected. It is yielded to the block defined by `Monitor#on_toggle_connection`.

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

You can retrieve the monitor



