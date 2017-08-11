# Marking a [`Window`](/deep-dive/window.md) for Closing

As described in [The Skeleton](/the-skeleton.md), the "close" status of a [`Window`](/deep-dive/window.md) is often used for loop control:

```crystal
until window.should_close?
  # application logic
end
```

A [`Window`](/deep-dive/window.md) is marked for closing either when a user "exes out" of it or when your application logic manually marks it. The window is not actually "closed" until it is [destroyed](/deep-dive/window/destroying-a-window.md). 

 ## `should_close?`
 You can check whether or not a [`Window`](/deep-dive/window.md) is currently marked for closing with the `should_close?` method:
 
```crystal
window = Window.new
window.should_close? # => false
```

`should_close?` returns `true` if the [`Window`](/deep-dive/window.md) is currently marked for closing, and returns `false` otherwise.

`should_close?` must be called from within a `run` block definition.
 
## `should_close` and `should_not_close`

If you'd like to manually mark a [`Window`](/deep-dive/window.md) for closing, you can do so with the `should_close` method:

```crystal
window.should_close? # => false

# manually mark the window for closing.
window.should_close

window.should_close? # => true
```

Alternatively, you can explicitly mark a [`Window`](/deep-dive/window.md) to *not* be closed with `should_not_close`:

```crystal
window.should_close? # => true

# manually mark the window for not closing
window.should_not_close

window.should_close? # => false
```

`should_close` and `should_not_close` must be called from within a `run` block definition.
   