# Screen Coordinates

Whenever and wherever possible, `CrystGLFW` uses *screen coordinates* as a unit of measurement on the screen. Conventional wisdom might suggest that screen coordinates map 1-to-1 to pixels on the screen, and although it is *possible* for this to be true on some machines, it is an awful assumption to make with your logic. 

There are only two exceptions to this rule. Anything dealing with a window's frame buffer is measured in actual pixels, and anything dealing with Images also deals directly with pixels. For everything else, screen coordinates are used.

It is highly recommended that you read the [coordinate systems section of the GLFW documentation](http://www.glfw.org/docs/latest/intro_guide.html#coordinate_systems) to gain a better understanding of screen coordinates.