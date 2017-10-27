# `CrystGLFW::Joystick`

A `CrystGLFW::Joystick` (or `Joystick`, for the purposes of this guide) represents a physical controller connected to the system. GLFW has 16 available joystick "slots", and a `Joystick` is simply a means of interacting with one of those slots. Internally `Joystick` is implemented as a Crystal Enum.

Joystick member names are derived from the names of the constants that represent them in the GLFW specification. The list of GLFW joysticks can be found [here](http://www.glfw.org/docs/latest/group__joysticks.html). Take the name of the constant, remove the "GLFW_JOYSTICK_" prefix and replace it with "Joystick::", and convert the rest to UpperCamelCase to get the name. For example:

`GLFW_JOYSTICK_1` is represented in `CrystGLFW` as `Joystick::One`.
`GLFW_JOYSTICK_2` is `Joystick::Two`.
`GLFW_JOYSTICK_LAST` is `Joystick::Last`.

And so on and so forth.

`Joystick` has one class method:

## `on_toggle_connection`

`on_toggle_connection` defines the desired callback behavior when a `Joystick` is either connected or disconnected.

```crystal
CrystGLFW::Joystick.on_toggle_connection do |event|
  if event.connected?
    puts "A joystick was just connected: #{event.joystick.name}"
  else
    puts "A joystick was just disconnected."
  end
end
```

`on_toggle_connection` yields a [`CrystGLFW::Event::JoystickToggleConnection`](/deep-dive/events/joysticktoggleconnection.md) to the block, and can be called from outside of a [`run`](/the-run-block.md) block definition.

## `connected?`

You can determine if a `Joystick` is currently connected using the `connected?` method:

```crystal
joystick.connected? # => Bool
```

`connected?` returns `true` if the joystick is connected, and `false` if not.

## `name`

You can retrieve the manufacturer's name for a `Joystick` using the `name` method:

```crystal
puts joystick.name if joystick.connected? # => String
```

Make sure you check that the `Joystick` is actually connected first!

## `axes`

You can retrieve the values of each axis on a `Joystick` using the `axes` method:

```crystal
joystick.axes if joystick.connected? # => Slice(Float32)
```

The return value is an enumerable Slice of `Float32`, each between -1.0 and 1.0.

Make sure you check that the `Joystick` is actually connected first!

## `buttons`

You can retrieve the state of each button on a `Joystick` using the `buttons` method:

```crystal
joystick.buttons if joystick.connected? # => Array(Bool)
```

The return value is an array of `Bool`, where `true` means that the button is pressed, and `false` means that the button is released.

Make sure you check that the `Joystick` is actually connected first!

## Checking Joysticks

Because `Joystick` is an Enum, question methods are available for each possible value of a given `Joystick`:

```crystal
CrystGLFW::Joystick.on_toggle_connection do |event|
  if event.joystick.one?
    puts "The joystick in slot 1 was just connected or disconnected."
  end
end
```