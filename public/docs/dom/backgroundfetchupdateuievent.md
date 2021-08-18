# BackgroundFetchUpdateUIEvent

The `BackgroundFetchUpdateUIEvent` interface of the [Background Fetch API](background_fetch_api) is an event type passed to <span class="page-not-created">`ServiceWorkerGlobalScope.onbackgroundfetchsuccess`</span> and <span class="page-not-created">`ServiceWorkerGlobalScope.onbackgroundfetchfail`</span>, and provides a method for updating the title and icon of the app to inform a user of the success or failure of a background fetch.

## Constructor

[`BackgroundFetchUpdateUIEvent()`](backgroundfetchupdateuievent/backgroundfetchupdateuievent)  
Creates a new `BackgroundFetchUIEvent` object. This constructor is not typically used, as the browser creates these objects itself and passed them to <span class="page-not-created">`ServiceWorkerGlobalScope.onbackgroundfetchsuccess`</span> and <span class="page-not-created">`ServiceWorkerGlobalScope.onbackgroundfetchfail`</span>.

## Properties

_This interface doesn't implement any specific properties, but inherits properties from [`Event`](event), and [`BackgroundFetchEvent`](backgroundfetchevent)._

## Methods

[`BackgroundFetchUpdateUIEvent.updateUI()`](backgroundfetchupdateuievent/updateui)  
Updates the title and icon in the user interface to show the status of a background fetch. Resolves with a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Examples

In this example, the `backgroundfetchsuccess` event is listened for, indicating that a fetch has completed successfully. The [`updateUI()`](backgroundfetchupdateuievent/updateui) method is then called, with a message to let the user know the episode they downloaded is ready.

    addEventListener('backgroundfetchsuccess', (event) => {
      const bgFetch = event.registration;

      event.waitUntil(async function() {
        // Create/open a cache.
        const cache = await caches.open('downloads');
        // Get all the records.
        const records = await bgFetch.matchAll();
        // Copy each request/response across.
        const promises = records.map(async (record) => {
          const response = await record.responseReady;
          await cache.put(record.request, response);
        });

        // Wait for the copying to complete.
        await Promise.all(promises);

        // Update the progress notification.
        event.updateUI({ title: 'Episode 5 ready to listen!' });
      }());
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#background-fetch-update-ui-event">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchUpdateUIEvent' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BackgroundFetchUpdateUIEvent`

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

`BackgroundFetchUpdateUIEvent`

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

`updateUI`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchUpdateUIEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchUpdateUIEvent</a>
