# BackgroundFetchRegistration.result

The `result` read-only property of the [`BackgroundFetchRegistration`](../backgroundfetchregistration) interface returns a string indicating whether the background fetch was successful or failed.

## Syntax

    let theResult = BackgroundFetchRegistration.result;

### Value

One of the following strings:

`""`  
The fetch is active so there is no result.

`"success"`  
The background fetch was successful.

`"failure"`  
The background fetch failed. This only appears when there is no ability for the browser to retry.

## Examples

Logging [`BackgroundFetchRegistration.result`](result) to the console returns a string indicating the status, or an empty string if the fetch is still active.

    console.log(bgFetch.result);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#dom-backgroundfetchregistration-result">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchRegistration.result' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`result`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/result" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/result</a>
