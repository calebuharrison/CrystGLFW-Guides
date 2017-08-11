# Polling/Waiting for Events
In order to process user input, errors, and other runtime events, GLFW has an internal event queue that must be monitored in some way in order for the events to be processed. CrystGLFW exposes this event queue primarily in two ways from within your application's main loop.

## `poll_events`
If your application needs to keep redrawing a window's buffer regardless of whether or not it receives events from the event queue, then `poll_events` is the choice for you:

```crystal
until window.should_close?
  CrystGLFW.poll_events
  window.swap_buffers
end
```
`poll_events` will check the event queue, process any of the events inside of that queue, and then immediately return, allowing the application to continue its execution of the loop. `poll_events` returns even if there are no events in the queue. This is perfect for games that need to continue rendering new frames even when the user remains idle.

Of course, `poll_events` must be called from within a [`run`](/the-run-block.md) block definition.

## `wait_events`
What if your application only needs to draw new frames upon receiving some sort of event in the queue? Say hello to `wait_events`:

```crystal
until window.should_close?
  CrystGLFW.wait_events
  window.swap_buffers
end
```
First, `wait_events` checks the event queue for any new events. If there are events to be processed, then `wait_events` processes those events and promptly returns, just like `poll_events`. If, on the other hand, there are no events in the event queue, then `wait_events` will put the thread to sleep until it detects that an event has been posted to the queue. This halts the application's execution and prevents the window from swapping its buffers until a new event comes along.

`wait_events` can optionally receive a timeout argument:

```crystal
until window.should_close?
  CrystGLFW.wait_events(1.5)
  window.swap_buffers
end
```
This forces `wait_events` to return at an interval of at least *timeout*. In this case, `wait_events` will return when it processes events in the queue *or* when 1.5 seconds have elapsed - whichever comes first.

`wait_events` is preferable to `poll_events` when possible, simply because it's less CPU-intensive. Many applications require `poll_events`, however - use the right tool for the job!

`wait_events` must be called from within a [`run`](/the-run-block.md) block definition.

## `post_empty_event`
If, for some reason, you need to force `wait_events` to return manually, you can do so with `post_empty_event`:

```crystal
CrystGLFW.post_empty_event # post a dummy event to the queue
```
This posts an empty event to the queue, forcing `wait_events` to wake the thread and return, resuming execution.

`post_empty_event` must be called from within a [`run`](/the-run-block.md) block definition.