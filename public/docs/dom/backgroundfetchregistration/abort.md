# BackgroundFetchRegistration.abort()

The `abort()` method of the [`BackgroundFetchRegistration`](../backgroundfetchregistration) interface aborts an active background fetch.

## Syntax

    let status = BackgroundFetchRegistration.abort();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with `true` if the fetch is successfulled aborted.

## Examples

Use `abort()` to terminate a background fetch that is in progress.

    bgFetch.abort();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#dom-backgroundfetchregistration-abort">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchRegistration.abort' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`abort`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/abort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/abort</a>
