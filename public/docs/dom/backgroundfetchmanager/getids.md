# BackgroundFetchManager.getIds()

The `getIds()` method of the [`BackgroundFetchManager`](../backgroundfetchmanager) interface returns the IDs of all registered background fetches.

## Syntax

    let stringArray = BackgroundFetchManager.getIds();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`strings`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).

### Exceptions

None.

## Examples

The following examples shows how to retrieve the IDs of all registered background fetches. With an active [`service worker`](../serviceworker), use the <span class="page-not-created">`ServiceWorkerRegistration.backgroundFetch`</span> property to access the \`BackgroundFetchManager\` object and call its \`get()\` method.

    navigator.serviceWorker.ready.then(async (swReg) => {
      const ids = await swReg.backgroundFetch.getIds();
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#background-fetch-manager-get-ids">Background Fetch<br />
<span class="small">The definition of 'getIds' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchManager/getIds" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchManager/getIds</a>
