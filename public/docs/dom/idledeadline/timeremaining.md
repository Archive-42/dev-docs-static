# IdleDeadline.timeRemaining()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The ` timeRemaining``() ` method on the [`IdleDeadline`](../idledeadline) interface returns the estimated number of milliseconds remaining in the current idle period. The callback can call this method at any time to determine how much time it can continue to work before it must return. For example, if the callback finishes a task and has another one to begin, it can call `timeRemaining()` to see if there's enough time to complete the next task. If there isn't, the callback can just return immediately, or look for other work to do with the remaining time.

By the time `timeRemaining()` reaches 0, it is suggested that the callback should return control to the user agent's event loop.

## Syntax

    timeRemaining = IdleDeadline.timeRemaining();

### Return value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) value (which is a floating-point number) representing the number of milliseconds the user agent estimates are left in the current idle period. The value is ideally accurate to within about 5 microseconds.

If the [`IdleDeadline`](../idledeadline) object's [`didTimeout`](didtimeout) property is true, this method returns zero.

## Example

See our [complete example](../background_tasks_api#example) in the article [Cooperative Scheduling of Background Tasks API](../background_tasks_api).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/requestidlecallback/">Cooperative Scheduling of Background Tasks</a></td><td><span class="spec-pr">Proposed Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

`timeRemaining`

47

79

55

No

34

No

47

47

55

34

No

5.0

## See also

- [Collaborative Scheduling of Background Tasks](../background_tasks_api)
- [`IdleDeadline`](../idledeadline)
- [`Window.requestIdleCallback()`](../window/requestidlecallback)
- [`Window.cancelIdleCallback()`](../window/cancelidlecallback)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IdleDeadline/timeRemaining" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IdleDeadline/timeRemaining</a>
