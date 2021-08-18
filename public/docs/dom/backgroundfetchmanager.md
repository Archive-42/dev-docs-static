# BackgroundFetchManager

The `BackgroundFetchManager` interface of the [Background Fetch API](background_fetch_api) is a map where the keys are background fetch IDs and the values are [`BackgroundFetchRegistration`](backgroundfetchregistration) objects.

## Properties

None.

## Methods

[`fetch()`](backgroundfetchmanager/fetch)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`BackgroundFetchRegistration`](backgroundfetchregistration) object for a supplied array of URLs and [`Request`](request) objects.

[`get()`](backgroundfetchmanager/get)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with the [`BackgroundFetchRegistration`](backgroundfetchregistration) associated with the provided `id` or [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) if the `id` is not found.

[`getIDs()`](backgroundfetchmanager/getids)  
Returns the IDs of all registered background fetches.

## Examples

The example below shows how to get an instance of [`BackgroundFetchManager`](backgroundfetchmanager) from a [`ServiceWorkerRegistration`](serviceworkerregistration) object and calls `fetch()` to download a video in the background.

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#background-fetch-manager">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchManager' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BackgroundFetchManager`

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

`fetch`

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

`get`

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

`getIds`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchManager" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchManager</a>
