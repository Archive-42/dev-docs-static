Window: storage event
=====================

The `storage` event of the [`Window`](../window) interface fires when a storage area (`localStorage`) has been modified in the context of another document.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../storageevent"><code>StorageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../windoweventhandlers/onstorage"><code>onstorage</code></a></td></tr></tbody></table>

Examples
--------

Log the `sampleList` item to the console when the `storage` event fires:

    window.addEventListener('storage', () => {
      // When local storage changes, dump the list to
      // the console.
      console.log(JSON.parse(window.localStorage.getItem('sampleList')));
    });

The same action can be achieved using the `onstorage` event handler property:

    window.onstorage = () => {
      // When local storage changes, dump the list to
      // the console.
      console.log(JSON.parse(window.localStorage.getItem('sampleList')));
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-storage">HTML Living Standard<br />
<span class="small">The definition of 'storage' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`storage_event`

1

≤18

45

?

15

?

≤37

18

45

14

?

1.0

See also
--------

-   [Web Storage API](../web_storage_api)
-   [Using the Web Storage API](../web_storage_api/using_the_web_storage_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/storage_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/storage_event</a>
