# `CrystGLFW::Event::WindowCursorCrossThreshold`

A `CrystGLFW::Event::WindowCursorCrossThreshold` is generated when the system cursor either enters or exits a `Window`. It is yielded to the block defined by `on_cursor_cross_threshold`.

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

You can retrieve the event's associated `Window` using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `cursor`

You can retrieve the `Cursor` associated with the `Window` using the `cursor` method:

```crystal
event.cursor # => CrystGLFW::Cursor
```

## `entered?`

You can determine whether or the cursor entered or exited the `Window` using the `entered?` method:

```crystal
event.entered?
```

`entered?` returns `true` if the cursor entered the `Window`, and returns `false` if the cursor exited it.
