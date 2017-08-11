# `CrystGLFW::Event::Modifiers`

The `Modifiers` module encapsulates logic associated with events that listen to modifier keys. The following events include modifier functionality:

- [`CrystGLFW::Event::WindowKey`](/deep-dive/events/windowkey.md)
- [`CrystGLFW::Event::WindowChar`](/deep-dive/events/windowcharacter.md)
- [`CrystGLFW::Event::WindowMouseButton`](/deep-dive/events/windowmousebutton.md)

These events have this additional interface:

## `shift?`

If you'd like to know if the shift key was held down, use the `shift?` method:

```crystal
event.shift? # => Bool
```

`shift?` returns `true` if the shift key was held, and returns `false` if it was not.

## `control?`

If you'd like to know if the control key was held down, use the `control?` method:

```crystal
event.control? # => Bool
```

`control?` returns `true` if the control key was held, and returns `false` if it was not.

## `alt?`

If you'd like to know if the alt key was held down, use the `alt?` method:

```crystal
event.alt? # => Bool
```

`alt?` returns `true` if the alt key was held, and returns `false` if it was not.

## `super?`

If you'd like to know if the super key (command on MacOS, windows key on Windows, etc.) was held down, use the `super?` method:

```crystal
event.super? # => Bool
```

`super?` returns `true` if the super key was held, and returns `false` if it was not.



