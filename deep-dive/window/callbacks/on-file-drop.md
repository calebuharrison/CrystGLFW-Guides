# `on_file_drop`

The `on_file_drop` method defines callback behavior that is triggered when one or more files are "drag-and-dropped" onto a `Window`. It generates a [`CrystGLFW::Event::WindowFileDrop`](/deep-dive/events/windowfiledrop.md) that is yielded to the block:

```crystal
window = Window.new

window.on_file_drop do |event|
  event.paths.each { |path| puts path }
end
```

With this callback defined, one or more files are dropped onto `window`, the absolute file path of each file is printed to standard output.

`on_file_drop` must be called from within a `run` block definition.