# `CrystGLFW::Joystick`

A `CrystGLFW::Joystick` (or `Joystick`, for the purposes of this guide) represents a physical controller connected to the system. GLFW has 16 available joystick "slots", and a `Joystick` is simply a means of interacting with one of those slots.

Joysticks can be identified through their *labels*. A label is simply a Crystal `Symbol` that references a specific `Joystick` slot. Joystick labels are derived from the names of the constants that represent them in the GLFW specification. The list of GLFW joysticks can be found [here](http://www.glfw.org/docs/latest/group__joysticks.html). Take the name of the constant, remove the "GLFW_" prefix, and convert it to a lowercase `Symbol` to get the label. For example:

`GLFW_JOYSTICK_1` is represented in `CrystGLFW` as `:joystick_1`.
`GLFW_JOYSTICK_2` is `:joystick_2`.
`GLFW_JOYSTICK_LAST` is `:joystick_last`.

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

## `new`

You can create a `Joystick` that interfaces with a joystick slot using the `new` method:

```crystal
joystick = CrystGLFW::Joystick.new(:joystick_1)
```

All you need to do is pass the joystick label that you'd like the instance to reference. The above example sets up a joystick that controls whatever is in the first joystick slot.

## `connected?`

You can determine if a `Joystick` is currently connected using the `connected?` method:

```crystal
joystick.connected? # => Bool
```

## `axes`

You can retrieve the values of each axis on a `Joystick` using the `axes` method:

```crystal
joystick = CrystGLFW::Joystick.new(:joystick_1)
joystick.axes # => Array(Float32)
```

The return value is an array of `Float32`, each between -1.0 and 1.0.

## `buttons`

You can retrieve the state of each button on a `Joystick` using the `buttons` method:

```crystal
joystick = CrystGLFW::Joystick.new(:joystick_1)
joystick.buttons # => Array(Bool)
```

The return value is an array of `Bool`, where `true` means that the button is pressed, and `false` means that the button is released.

## `is?`

You can use joystick labels to identify instances of `Joystick` using the `is?` method:

```crystal
CrystGLFW::Joystick.on_toggle_connection do |event|
  if event.joystick.is?(:joystick_1)
    puts "The joystick in slot 1 was just connected or disconnected."
  end
end
```

`is?` returns `true` if the given label matches the `Joystick`, and returns `false` otherwise.

You can pass an arbitrary number of labels, and `is?` will return `true` if any one of the labels matches the `Joystick`.

All `Joystick` functionality must be called from within a [`run`](/the-run-block.md) block definition.