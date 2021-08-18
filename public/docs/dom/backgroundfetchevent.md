# BackgroundFetchEvent

The `BackgroundFetchEvent` interface of the [Background Fetch API](background_fetch_api) is the event type for background fetch events dispatched on the [`service worker global scope`](serviceworkerglobalscope).

It is the event type passed to `onbackgroundfetchabort` and `onbackgroundfetchclick`.

## Constructor

[`BackgroundFetchEvent()`](backgroundfetchevent/backgroundfetchevent)  
Creates a new `BackgroundFetchEvent` object. This constructor is not typically used, as the browser creates these objects itself and provides them to background fetch event callbacks.

## Properties

_Inherits properties from its ancestor, [`Event`](event)_.

[`BackgroundFetchEvent.registration`](backgroundfetchevent/registration)<span class="badge inline readonly">Read only </span>  
Returns the [`BackgroundFetchRegistration`](backgroundfetchregistration) that the event was initialized to.

### Event handlers

None.

## Methods

None.

## Examples

In this example, if the user clicks on the user interface displaying the download progress, a new window will open. The current [`BackgroundFetchRegistration`](backgroundfetchregistration) is returned by calling `event.registration`.

    addEventListener('backgroundfetchclick', (event) => {
      const bgFetch = event.registration;

      if (bgFetch.result === 'success') {
        clients.openWindow('/latest-podcasts');
      } else {
        clients.openWindow('/download-progress');
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#background-fetch-event">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchEvent' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BackgroundFetchEvent`

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

`BackgroundFetchEvent`

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

`registration`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchEvent</a>
