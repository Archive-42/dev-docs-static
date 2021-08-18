# BackgroundFetchEvent.BackgroundFetchEvent()

The `BackgroundFetchEvent()` constructor creates a new [`BackgroundFetchEvent`](../backgroundfetchevent) object. This constructor is not typically used as the browser creates these objects itself and provides them to background fetch event callbacks.

## Syntax

    let BackgroundFetchEvent = new BackgroundFetchEvent(type, BackgroundFetchEventInit);

### Parameters

`type`  
A [`string`](../domstring) representing the name of the event. One of:

- `onbackgroundfetchabort`
- `onbackgroundfetchclick`

`BackgroundFetchEventInit`  
A [`BackgroundFetchRegistration`](../backgroundfetchregistration).

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchEvent/BackgroundFetchEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchEvent/BackgroundFetchEvent</a>
