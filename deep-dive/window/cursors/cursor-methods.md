# Cursor Methods

Cursors are objects in their own right in CrystGLFW, and therefore have a few methods that can be called on them.

## `window`

You can retrieve a `Cursor` object's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
window = cursor.window
```

The `window` method must be called from within a `run` block definition.

## `position`

The position of a `Cursor` can be retrieved using the `position` method:

```crystal
pos = cursor.position # => NamedTuple(x: Float64, y: Float64)
```

A cursor's position is always reported **relative to its window's position**. If a `Cursor` is precisely at the top-left corner of its associated [`Window`](/deep-dive/window.md), then its position is (0, 0).

`position` must be called from within a `run` block definition.

## `set_position` and `position=`

You can manually set the position of a `Cursor` using the `set_position` method:

```crystal
cursor.set_position(150, 150)
cursor.position # => NamedTuple(x: 150, y: 150)
```

Alternatively, you can use the `position=` method to achieve the same thing:

```crystal
cursor.position = {x: 150, y: 150}
cursor.position # => NamedTuple(x: 150, y: 150)
```

It's important to remember that a cursor's position is always reported and set **relative to its window's position**.

`set_position` and `position=` must be called from within a `run` block definition.

## `in_window?`

CrystGLFW provides all of the functionality to determine if a `Cursor` object is somewhere inside of its associated [`Window`](/deep-dive/window.md) object. You could make this calculation yourself - or you could just use the `in_window?` method:

```crystal
if cursor.in_window?
  puts "The cursor is in the window!"
else
  puts ":("
end
```

Obviously, `in_window?` returns `true` when the `Cursor` is inside of its [`Window`](/deep-dive/window.md), and returns `false` otherwise.

`in_window?` must be called from within a `run` block definition.