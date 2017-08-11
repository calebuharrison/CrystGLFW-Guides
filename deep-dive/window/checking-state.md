# Checking Window State

A [`Window`](/deep-dive/window.md) can be in several states, and these states can be checked independently from one another.

## `focused?`

The `focused?` method returns `true` if the [`Window`](/deep-dive/window.md) has input focus, and returns `false` otherwise:

```crystal
window = Window.new
window.focus

window.focused? # => true
```

`focused?` must be called from within a `run` block definition.

## `iconified?`

The `iconified?` method returns `true` if the [`Window`](/deep-dive/window.md) is iconified (minimized), and returns `false` otherwise:

```crystal
window = Window.new
window.iconified? # => false

window.iconify

window.iconified? # => true

window.restore

window.iconified? # => false
```

`iconified?` must be called from within a `run` block definition.

## `maximized?`

The `maximized?` method returns `true` if the [`Window`](/deep-dive/window.md) is maximized, and returns `false` otherwise:

```crystal
window = Window.new
window.maximized? # => false

window.maximize

window.maximized? # => true

window.restore

window.maximized? # => false
```

`maximized?` must be called from within a `run` block definition.

## `visible?`

The `visible?` method returns `true` if the [`Window`](/deep-dive/window.md) is visible to the user, and returns `false` otherwise:

```crystal
window = Window.new
window.visible? # => true

window.hide

window.visible? # => false

window.show

window.visible? # => true
```

`visible?` must be called from within a `run` block definition.

## `resizable?`

The `resizable?` method returns `true` if the [`Window`](/deep-dive/window.md) is not resizable by the user, and returns `false` otherwise:

```crystal
window = Window.new
window.resizable? # => true

hints = {:resizable => false}
window = Window.new(hints: hints)

window.resizable? # => false
```

`resizable?` must be called from within a `run` block definition.

## `decorated?`

The `decorated?` method returns `true` if the [`Window`](/deep-dive/window.md) is decorated by a border, and returns `false` otherwise:

```crystal
window = Window.new
window.decorated? # => true

hints = {:decorated => false}
window = Window.new(hints: hints)

window.decorated? # => false
```

`decorated?` must be called from within a `run` block definition.

## `floating?`

The `floating?` method returns `true` if the [`Window`](/deep-dive/window.md) is "floating" (fixed "above" other GUI windows), and returns `false` otherwise:

```crystal
window = Window.new
window.floating? # => false

hints = {:floating => true}
window = Window.new(hints: hints)

window.floating? # => true
```

`floating?` must be called from within a `run` block definition.