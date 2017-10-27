# Window Creation Hints

There are a number of constraints that can be placed on a `Window` and its context at the time of its creation. It is highly recommended that you read the [GLFW documentation's section on window hints](http://www.glfw.org/docs/latest/window_guide.html#window_hints) to gain an understanding of what each option does.

`CrystGLFW` requires that hints be placed in a `Hash` that is then passed to the window initializer. Although the documentation linked above provides helpful descriptions of each option, the table below should be referenced for how to construct your `Hash` while using `CrystGLFW`:

| Hint Label | Default Value | Supported Values |
| ---------- | ------------- | ---------------- |
| `Window::HintLabel::Resizable` | `true` | `true` or `false` |
| `Window::HintLabel::Visible` | `true` | `true` or `false` |
| `Window::HintLabel::Decorated` | `true` | `true` or `false` |
| `Window::HintLabel::Focused` | `true` | `true` or `false` |
| `Window::HintLabel::AutoIconify` | `true` | `true` or `false` |
| `Window::HintLabel::Floating` | `false` | `true` or `false` |
| `Window::HintLabel::Maximized` | `false` | `true` or `false` |
| `Window:HintLabel::RedBits` | 8 | Positive `Int32` or `CrystGLFW::DONT_CARE` |
| `Window::HintLabel::GreenBits` | 8 | Positive `Int32` or `CrystGLFW::DONT_CARE` |
| `Window::HintLabel::BlueBits` | 8 | Positive `Int32` or `CrystGLFW::DONT_CARE` |
| `Window::HintLabel::AlphaBits` | 8 | Positive `Int32` or `CrystGLFW::DONT_CARE` |
| `Window::HintLabel::DepthBits` | 24 | Positive `Int32` or `CrystGLFW::DONT_CARE` |
| `Window::HintLabel::StencilBits` | 8 | Positive `Int32` or `CrystGLFW::DONT_CARE` |
| `Window::HintLabel::AccumRedBits` | 0 | Positive `Int32` or `CrystGLFW::DONT_CARE` |
| `Window::HintLabel::AccumGreenBits` | 0 | Positive `Int32` or `CrystGLFW::DONT_CARE` |
| `Window::HintLabel::AccumBlueBits` | 0 | Positive `Int32` or `CrystGLFW::DONT_CARE` |
| `Window::HintLabel::AccumAlphaBits` | 0 | Positive `Int32` or `CrystGLFW::DONT_CARE` |
| `Window::HintLabel::AuxBuffers` | 0 | Positive `Int32` or `CrystGLFW::DONT_CARE` |
| `Window::HintLabel::Samples` | 0 | Positive `Int32` or `CrystGLFW::DONT_CARE` |
| `Window::HintLabel::RefreshRate` | `CrystGLFW::DONT_CARE` | Positive `Int32` or `CrystGLFW::DONT_CARE` |
| `Window::HintLabel::Stereo` | `false` | `true` or `false` |
| `Window::HintLabel::SRGBCapable` | `false` | `true` or `false` |
| `Window::HintLabel::Doublebuffer` | `true` | `true` or `false` |
| `Window::HintLabel::ClientAPI` | `ClientAPI::OpenGL` | any [`ClientAPI`](/clientapi.md) |
| `Window::HintLabel::ContextCreationAPI` | `ContextAPI::Native` | any [`ContextAPI`](/contextapi.md) |
| `Window::HintLabel::ContextVersionMajor` | 1 | Any valid major version number of the client API |
| `Window::HintLabel::ContextVersionMinor` | 0 | Any valid minor version number of the client API |
| `Window::HintLabel::ContextRobustness` | `ContextRobustness::None` | any [`ContextRobustness`](/contextrobustness.md) |
| `Window::HintLabel::ContextReleaseBehavior` | `ReleaseBehavior::Any` | any [`ReleaseBehavior`](/releasebehavior.md) |
| `Window::HintLabel::OpenGLForwardCompat` | `false` | `true` or `false` |
| `Window::HintLabel::OpenGLDebugContext` | `false` | `true` or `false` |
| `Window::HintLabel::OpenGLProfile` | `OpenGLProfile::Any` | any [`OpenGLProfile`](/openglprofile.md) |

## Examples

```crystal
hints = { 
  Window::HintLabel::ContextVersionMajor => 3,
  Window::HintLabel::ContextVersionMinor => 3,
  Window::HintLabel::OpenGLForwardCompat => true,
  Window::HintLabel::OpenGLProfile       => OpenGLProfile::Core,
  Window::HintLabel::ClientAPI           => ClientAPI::OpenGL
}
          
window = Window.new(hints: hints)
```