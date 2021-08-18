# BackgroundFetchRegistration.matchAll()

The `matchAll()` method of the [`BackgroundFetchRegistration`](../backgroundfetchregistration) interface returns an array of matching [`BackgroundFetchRecord`](../backgroundfetchrecord) objects.

## Syntax

    let records = BackgroundFetchRegistration.matchAll(request,options);

### Parameters

`request`  
The [`Request`](../request) for which you are attempting to find records. This can be a [`Request`](../request) object or a URL.

`options` <span class="badge inline optional">Optional</span>  
An object that sets options for the `match` operation. The available options are:

`ignoreSearch`  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that specifies whether to ignore the query string in the URL. For example, if set to `true` the `?value=bar` part of `http://foo.com/?value=bar` would be ignored when performing a match. It defaults to `false`.

`ignoreMethod`  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). When `true`, prevents matching operations from validating the [`Request`](../request) `http` method. If `false` (the default) only `GET` and `HEAD` are allowed.

`ignoreVary`  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). When `true` indicates that the [`VARY`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Vary) header should be ignored. It defaults to `false`.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an array of all matching [`BackgroundFetchRecord`](../backgroundfetchrecord) objects.

### Exceptions

`InvalidStateError`  
If the [`recordsAvailable`](recordsavailable) flag is `false`, indicating that there is not a fetch in progress, return a promise that resolves with an `InvalidStateError` [`DOMException`](../domexception).

## Examples

Use `matchAll()` with no parameters to return all of the records in a background fetch.

    const records = await bgFetch.matchAll();
    console.log(records); // an array of BackgroundFetchRecord objects

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#dom-backgroundfetchregistration-matchall">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchRegistration.matchAll' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`matchAll`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/matchAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/matchAll</a>
