# BackgroundFetchUpdateUIEvent.BackgroundFetchUpdateUIEvent()

The `BackgroundFetchUpdateUIEvent()` constructor creates a new [`BackgroundFetchUpdateUIEvent`](../backgroundfetchupdateuievent) object. This constructor is not typically used as the browser creates these objects itself and provides them to background fetch event callbacks.

## Syntax

    let BackgroundFetchEvent = new BackgroundFetchEvent(type, BackgroundFetchEventInit);

### Parameters

`type`  
A [`string`](../domstring) representing the name of the event. One of:

- `onbackgroundfetchsuccess`
- `onbackgroundfetchfail`

`BackgroundFetchEventInit`  
An object including the following:

A [`BackgroundFetchRegistration`](../backgroundfetchregistration).  
The background fetch registration instance.

`bubbles` <span class="badge inline optional">Optional</span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event bubbles. The default is `false`.

`cancelable` <span class="badge inline optional">Optional</span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event can be cancelled. The default is `false`.

`composed` <span class="badge inline optional">Optional</span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event will trigger listeners outside of a shadow root (see [`Event.composed`](../event/composed) for more details). The default is `false`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#backgroundfetchupdateuievent">Background Fetch<br />
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchUpdateUIEvent/BackgroundFetchUpdateUIEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchUpdateUIEvent/BackgroundFetchUpdateUIEvent</a>
