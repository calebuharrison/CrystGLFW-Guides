# Retrieving and Setting a Window's Title

The *title* of a [`Window`](/deep-dive/window.md) is usually displayed along the top of the window's frame. A *title* can be set upon the creation of a [`Window`](/deep-dive/window.md), but it can also be updated.
 
## `set_title` and `title=`

A window's title can be set with the `set_title` method:

```crystal
# window's title is "Winston the Window"
window = Window.new(title: "Winston the Window")

# window's title is now "Walter the Window"
window.set_title("Walter the Window")
```

Alternatively, you can use the `title=` method to achieve the same thing:

```crystal
# "Winston the Window"
window = Window.new(title: "Winston the Window")

# "Walter the Window"
window.title = "Walter the Window"
```

`set_title` and `title=` must be called from within a [`run`](/the-run-block.md) block definition.