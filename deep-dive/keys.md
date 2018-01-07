# `CrystGLFW::Key`

A `CrystGLFW::Key` \(or `Key`, for the purposes of this guide\) represents an individual key on the keyboard. Internally, `Key` is implemented as a Crystal Enum.

Key member names are derived from the names of the constants that represent them in the GLFW specification. The list of GLFW keys can be found [here](http://www.glfw.org/docs/latest/group__keys.html). Take the name of the constant, remove the "GLFW_KEY_" prefix and replace it with "Key::", and convert the rest of the key name to UpperCamelCase to get the member name. For example:

`GLFW_KEY_A` is represented in `CrystGLFW` as `Key::A`.  
`GLFW_KEY_LEFT_SHIFT` is `Key::LeftShift`.  
`GLFW_KEY_EQUAL` is `:key::Equal`.

And so on and so forth. A drawback of this approach is that key names that begin with a number must have that number spelled out:

`GLFW_KEY_0` is represented in `CrystGLFW` as `Key::Zero`.  
`GLFW_Key_F1` is simply `Key::F1`, because it does not begin with a number.

Note: You'll want to \[check this GLFW docs page\]\(http://www.glfw.org/docs/latest/group\_\_keys.html\) if you're using a non-US keyboard and are confused by the results.

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
  key = event.key
  puts key.name if key.printable?
end
```

If the `Key` is not printable, an exception will be raised.

## Checking Keys

Because `Key` is an Enum, question methods are available for each possible value of a given `Key`:

```crystal
window.on_key do |event|
  key = event.key
  if key.a?
    puts "key a was pressed"
  elsif key.b?
    puts "key b was pressed"
  elsif key.caps_lock?
    puts "caps lock was pressed"
  else
    puts "other key"
  end
end
```



