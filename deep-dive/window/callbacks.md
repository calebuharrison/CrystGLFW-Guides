# Window Callbacks

`CrystGLFW` provides idiomatic callback support for several different kinds of events. Each callback generates its own subclass of [`CrystGLFW::Event::Any`](/deep-dive/events.md), which is then yielded to the block defined by the method call. This section enumerates the different kinds of callbacks that can be defined on instances of [`Window`](/deep-dive/window.md).

