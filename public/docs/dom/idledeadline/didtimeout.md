# IdleDeadline.didTimeout

The read-only `didTimeout` property on the **[`IdleDeadline`](../idledeadline)** interface is a Boolean value which indicates whether or not the idle callback is being invoked because the timeout interval specified when [`Window.requestIdleCallback()`](../window/requestidlecallback) was called has expired.

If `didTimeout` is `true`, the `IdleDeadline` object's [`timeRemaining()`](timeremaining) method will return approximately 0.

Idle callbacks support the concept of a timeout in order to ensure that whatever task they're meant to perform actually happens, even if the user agent never has enough idle time available. Your callback will typically check the value of `didTimeout` if it needs to perform an action even if the browser is too busy to grant you the time; you should react by performing the needed task or, ideally, a minimal amount of work that can be done to keep things moving along, then schedule a new callback to try again to get the rest of the work done.

## Syntax

    var timedOut = IdleDeadline.didTimeout;

### Value

A Boolean which is `true` if the callback is running due to the callback's timeout period elapsing or `false` if the callback is running because the user agent is idle and is offering time to the callback.

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

`didTimeout`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IdleDeadline/didTimeout" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IdleDeadline/didTimeout</a>
