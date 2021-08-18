# BackgroundFetchRecord

The `BackgroundFetchRecord` interface of the [Background Fetch API](background_fetch_api) represents an individual request and response.

A `BackgroundFetchRecord` is created by the [`BackgroundFetchManager.fetch()`](backgroundfetchmanager/fetch) method, therefore there is no constructor for this interface.

There will be one `BackgroundFetchRecord` for each resource requested by `fetch()`.

## Properties

[`request`](backgroundfetchrecord/request)<span class="badge inline readonly">Read only </span>  
Returns a [`Request`](request).

[`responseReady`](backgroundfetchrecord/responseready)<span class="badge inline readonly">Read only </span>  
Returns a promise that resolves with a [`Response`](response).

## Examples

In this example an individual `BackgroundFetchRecord` is returned using [`BackgroundFetchManager.fetch()`](backgroundfetchmanager/fetch). The [`BackgroundFetchRecord.request`](backgroundfetchrecord/request) and [`BackgroundFetchRecord.responseReady`](backgroundfetchrecord/responseready) are returned and logged to the console.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#background-fetch-record-interface">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchRecord' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BackgroundFetchRecord`

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

`request`

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

`responseReady`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRecord" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRecord</a>
