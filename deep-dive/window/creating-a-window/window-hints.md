# Window Creation Hints

There are a number of constraints that can be placed on a `Window` and its context at the time of its creation. It is highly recommended that you read the [GLFW documentation's section on window hints](http://www.glfw.org/docs/latest/window_guide.html#window_hints) to gain an understanding of what each option does.

`CrystGLFW` requires that hints be placed in a `Hash` that is then passed to the window initializer. Although the documentation linked above provides helpful descriptions of each option, the table below should be referenced for how to construct your `Hash`:

| Hint Label | Default Value | Supported Values |
| ---------- | ------------- | ---------------- |
| `:resizable` | `true` | `true` or `false` |
| `:visible` | `true` | `true` or `false` |
| `:decorated` | `true` | `true` or `false` |
| `:focused` | `true` | `true` or `false` |
| `:auto_iconify` | `true` | `true` or `false` |
| `:floating` | `false` | `true` or `false` |
| `:maximized` | `false` | `true` or `false` |
| `:red_bits` | 8 | Positive `Int32` or `:dont_care` |
| `:green_bits` | 8 | Positive `Int32` or `:dont_care` |
| `:blue_bits` | 8 | Positive `Int32` or `:dont_care` |
| `:alpha_bits` | 8 | Positive `Int32` or `:dont_care` |
| `:depth_bits` | 24 | Positive `Int32` or `:dont_care` |
| `:stencil_bits` | 8 | Positive `Int32` or `:dont_care` |
| `:accum_red_bits` | 0 | Positive `Int32` or `:dont_care` |
| `:accum_green_bits` | 0 | Positive `Int32` or `:dont_care` |
| `:accum_blue_bits` | 0 | Positive `Int32` or `:dont_care` |
| `:accum_alpha_bits` | 0 | Positive `Int32` or `:dont_care` |
| `:aux_buffers` | 0 | Positive `Int32` or `:dont_care` |
| `:samples` | 0 | Positive `Int32` or `:dont_care` |
| `:refresh_rate` | `:dont_care` | Positive `Int32` or `:dont_care` |
| `:stereo` | `false` | `true` or `false` |
| `:srgb_capable` | `false` | `true` or `false` |
| `:doublebuffer` | `true` | `true` or `false` |
| `:client_api` | `:opengl_api` | `:opengl_api`, `:opengl_es_api`, or `:no_api` |
| `:context_creation_api` | `:native_context_api` | `:native_context_api` or `:egl_context_api` |
| `:context_version_major` | 1 | Any valid major version number of the client API |
| `:context_version_minor` | 0 | Any valid minor version number of the client API |
| `:context_robustness` | `:no_robustness` | `:no_robustness`, `:no_reset_notification`, or `:lose_context_on_reset` |
| `:context_release_behavior` | `:any_release_behavior` | `:any_release_behavior`, `:release_behavior_flush`, or `:release_behavior_none` |
| `:opengl_forward_compat` | `false` | `true` or `false` |
| `:opengl_debug_context` | `false` | `true` or `false` |
| `:opengl_profile` | `:opengl_any_profile` | `:opengl_any_profile`, `:opengl_compat_profile`, or `:opengl_core_profile` |