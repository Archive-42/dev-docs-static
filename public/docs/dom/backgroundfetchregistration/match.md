# BackgroundFetchRegistration.match()

The `match()` method of the [`BackgroundFetchRegistration`](../backgroundfetchregistration) interface returns the first matching [`BackgroundFetchRecord`](../backgroundfetchrecord).

## Syntax

    let record = BackgroundFetchRegistration.match(request, options);

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

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with the first [`BackgroundFetchRecord`](../backgroundfetchrecord) that matches the request or [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) if no match is found.

**Note**: `BackgroundFetchRegistration.match()` is basically identical to [`BackgroundFetchRegistration.matchAll()`](matchall), except that rather than resolving with an array of all matching records, it resolves with the first matching record only.

### Exceptions

`InvalidStateError`  
A [`DOMException`](../domexception) indicating that you called `match()` when there are no fetches in progress. This state will be reflected by [`BackgroundFetchRegistration.recordsAvailable`](recordsavailable) being set to `false`

## Examples

In this example we look for a record with the url "/ep-5.mp3". If a [`BackgroundFetchRecord`](../backgroundfetchrecord) is found then we can return some information about it.

    bgFetch.match('/ep-5.mp3').then(async (record) => {
      if (!record) {
        console.log('No record found');
        return;
      }

      console.log(`Here's the request`, record.request);
      const response = await record.responseReady;
      console.log(`And here's the response`, response);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#dom-backgroundfetchregistration-match">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchRegistration.match' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`match`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/match" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/match</a>
