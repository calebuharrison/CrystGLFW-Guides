# `CrystGLFW::Event::WindowFileDrop`

A `CrystGLFW::Event::WindowFileDrop` is generated when one or more files are "drag-and-dropped" onto a [`Window`](/deep-dive/window.md). It is yielded to the block defined by [`on_file_drop`](/deep-dive/window/callbacks/on-file-drop.md).

```crystal
window = Window.new

window.on_file_drop do |event|
  event.paths.each { |path| puts path }
end
```

## `window`

You can retrieve the event's associated [`Window`](/deep-dive/window.md) using the `window` method:

```crystal
event.window # => CrystGLFW::Window
```

## `paths`

You can retrieve the absolute file paths of the dropped files using the `paths` method:

```crystal
event.paths # => Array(String)
```


