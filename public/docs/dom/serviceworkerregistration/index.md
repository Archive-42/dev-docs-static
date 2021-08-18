ServiceWorkerRegistration.index
===============================

**Draft**

This page is not complete.

The `index` read-only property of the [`ServiceWorkerRegistration`](../serviceworkerregistration) interface returns a reference to the [`ContentIndex`](../contentindex) interface, which allows for indexing of offline content.

Syntax
------

    var contentIndexObject = ServiceWorkerRegistration.index;

### Value

A ContentIndex [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

Examples
--------

You can access the property from either your main script or the registered service worker.

Here is an example from the main script:

    // reference registration
    const registration = await navigator.serviceWorker.ready;

    // feature detection
    if ('index' in registration) {

      // Content Index API functionality
      const contentIndex = registration.index;

    }

From the [`service worker`](../serviceworker):

    // service worker script

    const contentIndex = self.registration.index;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/content-index/spec/#extensions-to-service-worker-registration">Content Index API<br />
<span class="small">The definition of 'index' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`index`

No

No

No

No

No

No

Yes

Yes

No

Yes

No

No

See also
--------

-   [`Content Index API`](../content_index_api)
-   [An introductory article on the Content Index API](https://web.dev/content-indexing-api/)
-   [An app which uses the Content Index API to list and remove 'save for later' content](https://contentindex.dev/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/index" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/index</a>
