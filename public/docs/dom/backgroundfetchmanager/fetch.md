# BackgroundFetchManager.fetch()

The `fetch()` method of the [`BackgroundFetchManager`](../backgroundfetchmanager) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`BackgroundFetchRegistration`](../backgroundfetchregistration) object for a supplied array of URLs and [`Request`](../request) objects.

## Syntax

    let backgroundFetchRegistration = BackgroundFetchManager.fetch(id, requests [,options]);

### Parameters

`id`  
A developer-defined identifier that can be passed to the other methods to retrieve a [`backgroundFetchRegistration`](../backgroundfetchregistration).

`requests`  
A <span class="page-not-created">`RequestInfo`</span> object or an array of such objects.

`options` <span class="badge inline optional">Optional</span>  
A <span class="page-not-created">`BackgroundFetchOptions`</span> object.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`BackgroundFetchRegistration`](../backgroundfetchregistration) object.

### Exceptions

TypeError  
Raised if no request is provided, if the mode of a request is 'no-cors', if no service worker is present, a request already exists with the requested `id`, or the request fails.

DOMException  
This method may raise a [`DOMException`](../domexception) of the following types:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>AbortError</code></td><td><p>Indicates the fetch was aborted.</p></td></tr><tr class="even"><td><code>NotAllowedError</code></td><td><p>Indicates that user permission has not been granted to make background fetches.</p></td></tr></tbody></table>

## Examples

The following examples shows how to use `fetch()` to create a [`BackgroundFetchRegistration`](../backgroundfetchregistration). With an active [`service worker`](../serviceworker), use the <span class="page-not-created">`ServiceWorkerRegistration.backgroundFetch`</span> property to access the `BackgroundFetchManager` object and call its `fetch()` method.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#background-fetch-manager-fetch">Background Fetch<br />
<span class="small">The definition of 'fetch' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchManager/fetch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchManager/fetch</a>
