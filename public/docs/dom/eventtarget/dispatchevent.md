EventTarget.dispatchEvent()
===========================

Dispatches an [`Event`](../event) at the specified [`EventTarget`](../eventtarget), (synchronously) invoking the affected [`EventListener`](../eventlistener)s in the appropriate order. The normal event processing rules (including the capturing and optional bubbling phase) also apply to events dispatched manually with `dispatchEvent()`.

Syntax
------

    cancelled = !target.dispatchEvent(event)

### Parameter

-   `event` is the [`Event`](../event) object to be dispatched.
-   `target` is used to initialize the [`Event.target`](../event/target) and determine which event listeners to invoke.

### Return Value

-   The return value is `false` if `event` is cancelable and at least one of the event handlers which received `event` called [`Event.preventDefault()`](../event/preventdefault). Otherwise it returns `true`.

The `dispatchEvent()` method throws `UNSPECIFIED_EVENT_TYPE_ERR` if the event's type was not specified by initializing the event before the method was called, or if the event's type is `null` or an empty string.

### Exceptions

Exceptions thrown by event handlers are reported as uncaught exceptions. The event handlers run on a nested callstack; they block the caller until they complete, but exceptions do not propagate to the caller.

Notes
-----

Unlike "native" events, which are fired by the DOM and invoke event handlers asynchronously via the [event loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop), `dispatchEvent()` invokes event handlers synchronously. All applicable event handlers will execute and return before the code continues on after the call to `dispatchEvent()`.

`dispatchEvent()` is the last step of the create-init-dispatch process, which is used for dispatching events into the implementation's event model. The event can be created using [Event constructor](../event/event).

See also the [Event object reference](../event).

Example
-------

See [Creating and triggering events](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-eventtarget-dispatchevent">DOM<br />
<span class="small">The definition of 'EventTarget.dispatchEvent()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition in the DOM 2 Events specification.</td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`dispatchEvent`

4

12

2

9

6-11

Older versions of IE supported an equivalent, proprietary `EventTarget.fireEvent()` method.

9

3.2

4

18

4

10.1

3

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/dispatchEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/dispatchEvent</a>
