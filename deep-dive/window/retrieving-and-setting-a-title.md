# Retrieving and Setting a Window's Title

The *title* of a `Window` is usually displayed along the top of the window's frame. A *title* can be set upon the creation of a `Window`, but it can also be retrieved and updated.
 
## `title`

You can retrieve the current title of a `Window` object using the `title` method:

```crystal
window = Window.new(title: "Winston the Window")
window.title # => "Winston the Window"
```
 
`title` must be called from within a `run` block definition.
 
## `set_title` and `title=`

A window's title can be set with the `set_title` method:

```crystal
window = Window.new(title: "Winston the Window")
window.title # => "Winston the Window"

window.set_title("Walter the Window")
window.title # => "Walter the Window"
```

Alternatively, you can use the `title=` method to achieve the same thing:

```crystal
window = Window.new(title: "Winston the Window")
window.title # => "Winston the Window"

window.title = "Walter the Window"
window.title # => "Walter the Window"
```

`set_title` and `title=` must be called from within a `run` block definition.