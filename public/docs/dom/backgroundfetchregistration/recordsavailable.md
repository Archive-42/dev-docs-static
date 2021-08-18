# BackgroundFetchRegistration.recordsAvailable

The `recordsAvailable` read-only property of the [`BackgroundFetchRegistration`](../backgroundfetchregistration) interface returns `true` if there are requests and responses to be accessed. If this returns false then [`match()`](match) and [`matchAll()`](matchall) can't be used.

## Syntax

    let recordsAvailable = BackgroundFetchRegistration.recordsAvailable;

### Value

A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

## Examples

Logging [`BackgroundFetchRegistration.recordsAvailable`](recordsavailable) to the console returns `true` or `false` to indicate if there are records.

    console.log(bgFetch.recordsAvailable);

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#dom-backgroundfetchregistration-recordsavailable">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchRegistration.recordsAvailable' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`recordsAvailable`

74

79

No

No

62

No

No

74

No

53

No

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/recordsAvailable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/recordsAvailable</a>
