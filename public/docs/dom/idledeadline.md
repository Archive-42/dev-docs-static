# IdleDeadline

The `IdleDeadline` interface is used as the data type of the input parameter to idle callbacks established by calling [`Window.requestIdleCallback()`](window/requestidlecallback). It offers a method, [`timeRemaining()`](idledeadline/timeremaining), which lets you determine how much longer the user agent estimates it will remain idle and a property, [`didTimeout`](idledeadline/didtimeout), which lets you determine if your callback is executing because its timeout duration expired.

To learn more about how request callbacks work, see [Collaborative Scheduling of Background Tasks](background_tasks_api).

## Properties

[`IdleDeadline.didTimeout`](idledeadline/didtimeout) <span class="badge inline readonly">Read only </span>  
A Boolean whose value is `true` if the callback is being executed because the timeout specified when the idle callback was installed has expired.

## Methods

[`IdleDeadline.timeRemaining()`](idledeadline/timeremaining)  
Returns a [`DOMHighResTimeStamp`](domhighrestimestamp), which is a floating-point value providing an estimate of the number of milliseconds remaining in the current idle period. If the idle period is over, the value is 0. Your callback can call this repeatedly to see if there's enough time left to do more work before returning.

## Example

See our [complete example](background_tasks_api#example) in the article [Cooperative Scheduling of Background Tasks API](background_tasks_api).

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

`IdleDeadline`

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

- [Cooperative Scheduling of Background Tasks API](background_tasks_api)
- [`Window.requestIdleCallback()`](window/requestidlecallback)
- [`Window.cancelIdleCallback()`](window/cancelidlecallback)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IdleDeadline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IdleDeadline</a>
