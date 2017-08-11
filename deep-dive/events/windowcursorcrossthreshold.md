# `CrystGLFW::Event::WindowCursorCrossThreshold`

A `CrystGLFW::Event::WindowCursorCrossThreshold` is generated when the system cursor either enters or exits a [`Window`](/deep-dive/window.md). It is yielded to the block defined by [`on_cursor_cross_threshold`](/deep-dive/window/callbacks/on-cursor-cross-threshold.md).

```crystal
window = Window.new

window.on_cursor_cross_threshold do |event|
  if event.entered?
    puts "cursor entered window"
  else
    puts "cursor exited window"
  end
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `cursor`

You can retrieve the [`Cursor`](/deep-dive/window/cursors.md) associated with the [`Window`](/deep-dive/window.md) using the `cursor` method:

```crystal
event.cursor # => CrystGLFW::Cursor
```

## `entered?`

You can determine whether or the cursor entered or exited the [`Window`](/deep-dive/window.md) using the `entered?` method:

```crystal
event.entered?
```

`entered?` returns `true` if the cursor entered the [`Window`](/deep-dive/window.md), and returns `false` if the cursor exited it.
