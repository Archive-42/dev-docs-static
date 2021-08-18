# BackgroundFetchRegistration.failureReason

The `failureReason` read-only property of the [`BackgroundFetchRegistration`](../backgroundfetchregistration) interface returns a string with a value that indicates a reason for a background fetch failure.

## Syntax

    let failureReason = BackgroundFetchRegistration.failureReason;

### Value

One of the following strings:

`""`  
The background fetch has not completed, or was successful.

`"aborted"`  
The operation was cancelled by the user, or [`abort()`](abort) was called.

`"bad-status"`  
A response had a not-ok status (a status outside the range 200-299).

`"fetch-error"`  
A fetch failed for other reasons, for example CORS, or a network failure.

`"quota-exceeded"`  
Storage quota was reached during the operation.

`"download-total-exceeded"`  
The provided `downloadTotal` was exceeded. This value was set when the background fetch was registered.

## Examples

Logging [`BackgroundFetchRegistration.failureReason`](failurereason) to the console prints the reason the fetch failed, or an empty string if it was successful or has not yet completed.

    console.log(bgFetch.failureReason);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#dom-backgroundfetchregistration-failurereason">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchRegistration.failureReason' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`failureReason`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/failureReason" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/failureReason</a>
