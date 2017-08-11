# `CrystGLFW::Events::JoystickToggleConnection`

A `CrystGLFW::Event::JoystickToggleConnection` is generated when a [`Joystick`](/deep-dive/joysticks.md) is either connected or disconnected. It is yielded to the block defined by [`Joystick#on_toggle_connection`](/deep-dive/joysticks.md).

```crystal
CrystGLFW::Joystick.on_toggle_connection do |event|
  if event.connected?
    puts "A joystick was just connected: #{event.joystick.name}"
  else
    puts "A monitor was just disconnected."
  end
end
```

## `joystick`

You can retrieve the joystick that was connected/disconnected using the `joystick` method:

```crystal
event.joystick # => CrystGLFW::Joystick
```

## `connected?`

You can use the `connected?` method to determine if the [`Joystick`](/deep-dive/joysticks.md) was connected or disconnected:

```crystal
event.connected? # => Bool
```

`connected?` returns `true` if the [`Joystick`](/deep-dive/joysticks.md) was connected, and returns `false` if it was disconnected.



