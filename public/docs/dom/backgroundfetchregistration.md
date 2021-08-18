# BackgroundFetchRegistration

The `BackgroundFetchRegistration` interface of the [Background Fetch API](background_fetch_api) represents an individual background fetch.

A `BackgroundFetchRegistration` instance is returned by the [`BackgroundFetchManager.fetch()`](backgroundfetchmanager/fetch) or [`BackgroundFetchManager.get()`](backgroundfetchmanager/get) methods, and therefore there has no constructor.

## Properties

The following properties are available synchronously, as convenience properties copied from those in the `BackgroundFetchRegistration` instance.

[`BackgroundFetchRegistration.id`](backgroundfetchregistration/id)<span class="badge inline readonly">Read only </span>  
A [`string`](domstring) containing the background fetch's ID.

[`BackgroundFetchRegistration.uploadTotal`](backgroundfetchregistration/uploadtotal)<span class="badge inline readonly">Read only </span>  
A [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) containing the total number of bytes to be uploaded.

[`BackgroundFetchRegistration.uploaded`](backgroundfetchregistration/uploaded)<span class="badge inline readonly">Read only </span>  
A [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) containing the size in bytes successfully sent, initially `0`.

[`BackgroundFetchRegistration.downloadTotal`](backgroundfetchregistration/downloadtotal)<span class="badge inline readonly">Read only </span>  
A [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) containing the total size in bytes of this download. This is the value set when the background fetch was registered, or `0`.

[`BackgroundFetchRegistration.downloaded`](backgroundfetchregistration/downloaded)<span class="badge inline readonly">Read only </span>  
A [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) containing the size in bytes that has been downloaded, initially `0`.

[`BackgroundFetchRegistration.result`](backgroundfetchregistration/result)<span class="badge inline readonly">Read only </span>  
Returns an empty string initially, on completion either the string `"success"` or `"failure"`.

[`BackgroundFetchRegistration.failureReason`](backgroundfetchregistration/failurereason)<span class="badge inline readonly">Read only </span>  
One of the following strings:

`""`  
The background fetch has not completed, or was successful.

`"aborted"`  
The operation was cancelled by the user, or [`abort()`](backgroundfetchregistration/abort) was called.

`"bad-status"`  
A response had a not-ok status (a status outside the range 200-299).

`"fetch-error"`  
A fetch failed for other reasons, for example CORS, or a network failure.

`"quota-exceeded"`  
Storage quota was reached during the operation.

`"download-total-exceeded"`  
The provided `downloadTotal` was exceeded. This value was set when the background fetch was registered.

[`BackgroundFetchRegistration.recordsAvailable`](backgroundfetchregistration/recordsavailable)<span class="badge inline readonly">Read only </span>  
A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the `recordsAvailable` flag is set.

### Event handlers

[`BackgroundFetchRegistration.onprogress`](backgroundfetchregistration/onprogress)  
Fired when there is a change to any of the following properties:

- `uploaded`
- `downloaded`
- `result`
- `failureReason`

## Methods

[`BackgroundFetchRegistration.abort()`](backgroundfetchregistration/abort)  
Aborts the background fetch. Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with `true` if the fetch was successfully aborted.

[`BackgroundFetchRegistration.match()`](backgroundfetchregistration/match)  
Returns a single [`BackgroundFetchRecord`](backgroundfetchrecord) object which is the first match for the arguments.

[`BackgroundFetchRegistration.matchAll()`](backgroundfetchregistration/matchall)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an array of [`BackgroundFetchRecord`](backgroundfetchrecord) objects containing requests and responses.

## Examples

The following code creates a `BackGroundFetchRegistration` as `bgFetch`, with an `id` of `"my-fetch"`.

    navigator.serviceWorker.ready.then(async (swReg) => {
      const bgFetch = await swReg.backgroundFetch.fetch('my-fetch', ['/ep-5.mp3', 'ep-5-artwork.jpg'], {
        title: 'Episode 5: Interesting things.',
        icons: [{
          sizes: '300x300',
          src: '/ep-5-icon.png',
          type: 'image/png',
        }],
        downloadTotal: 60 * 1024 * 1024,
      });
    });

Logging the [`id`](backgroundfetchregistration/id) to the console returns `"my-fetch"`.

    console.log(bgFetch.id); // "my-fetch"

The [`match()`](backgroundfetchregistration/match) method can be used to find a particular [`BackgroundFetchRecord`](backgroundfetchrecord) from those that are part of the registration.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#background-fetch-registration">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchRegistration' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BackgroundFetchRegistration`

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

`downloaded`

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

`downloadTotal`

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

`id`

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

`onprogress`

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

`uploaded`

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

`uploadTotal`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration</a>
