# `CrystGLFW::Key`

A `CrystGLFW::Key` (or `Key`, for the purposes of this guide) represents an individual key on the keyboard. Currently, you cannot create a `Key` directly - they are created and destroyed internally.

Keys can be identified through their *labels*. A label is simply a Crystal `Symbol` that references a specific `Key`. Key labels are derived from the names of the constants that represent them in the GLFW specification. The list of GLFW keys can be found [here](http://www.glfw.org/docs/latest/group__keys.html). Take the name of the constant, remove the "GLFW_" prefix, and convert it to a lowercase `Symbol` to get the label. For example:

`GLFW_KEY_A` is represented in `CrystGLFW` as `:key_a`.
`GLFW_KEY_LEFT_SHIFT` is `:key_left_shift`.
`GLFW_KEY_EQUAL` is `:key_equal`.

And so on and so forth.

## `printable?`

GLFW makes a distinction between "printable" keys and "non-printable" keys. You can see if a `Key` is printable by using the `printable?` method:

```crystal
window.on_key do |event|
  puts event.key.printable? # => Bool
end
```

`printable?` returns `true` if the `Key` is printable, and returns `false` if it is not.

## `name`

If a `Key` is "printable", then it has an internal name. You can retrieve this name using the `name` method:

```crystal
window.on_key do |event|
  puts event.key.name if key.printable?
end
```

If the `Key` is not printable, an exception will be raised.

## `is?`

You can use key labels to identify instances of `Key` using the `is?` method:

```crystal
window.on_key do |event|
  key = event.key
  if key.is?(:key_a)
    puts "key a"
  elsif key.is?(:key_b)
    puts "key b"
  else
    puts "other key"
  end
end
```

`is?` returns `true` if the given label matches the `Key`, and returns `false` otherwise.

You can pass an arbitrary number of labels, and `is?` will return `true` if any one of the labels matches the `Key`:

```crystal
window.on_key do |event|
  key = event.key
  if key.is?(:key_a, :key_b, :key_c)
    puts "A, B, or C!"
  elsif key.is?(:key_1, :key_2, :key_3)
    puts "1, 2, or 3!"
  else
    puts "no."
  end
end
```

All `Key` functionality must be called from within a [`run`](/the-run-block.md) block definition.