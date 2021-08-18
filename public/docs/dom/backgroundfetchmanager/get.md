# BackgroundFetchManager.get()

The `get()` method of the [`BackgroundFetchManager`](../backgroundfetchmanager) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with the [`BackgroundFetchRegistration`](../backgroundfetchregistration) associated with the provided `id` or [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) if the `id` is not found.

## Syntax

    let backgroundFetchRegistration = BackgroundFetchManager.get(id);

### Parameters

`id`  
the ID of a [`backgroundFetchRegistration`](../backgroundfetchregistration) defined by calling <span class="page-not-created">`fetch()`</span>.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`BackgroundFetchRegistration`](../backgroundfetchregistration) or <span class="page-not-created">`undeffined`</span>.

## Examples

The following examples shows how to use `get()` to retrieve a [`BackgroundFetchRegistration`](../backgroundfetchregistration). With an active [`service worker`](../serviceworker), use the <span class="page-not-created">`ServiceWorkerRegistration.backgroundFetch`</span> to access the `BackgroundFetchManager` object and call its `get()` method.

    navigator.serviceWorker.ready.then(async (swReg) => {
      const bgFetch = await swReg.backgroundFetch.get('my-fetch');
    });
    my code block

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#background-fetch-manager-get">Background Fetch<br />
<span class="small">The definition of 'get' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchManager/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchManager/get</a>
