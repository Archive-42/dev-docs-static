# PushEvent.PushEvent()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PushEvent()` constructor creates a new [`PushEvent`](../pushevent) object. Note that the this constructor is exposed only to a service worker context.

## Syntax

    var myPushEvent = new PushEvent(type, eventInitDict);

### Parameters

_type_  
A [`DOMString`](../domstring) defining the type of `PushEvent`. This can be `push` or `pushsubscriptionchange`.

_eventInitDict_ <span class="badge inline optional">Optional</span>  
An options object containing any initialization data you want to populate the `PushEvent` object with. The options are:

- `data`: The data you want the `PushEvent` to contain, if any. When the constructor is invoked, the [`PushEvent.data`](data) property of the resulting object will be set to a new [`PushMessageData`](../pushmessagedata) object containing bytes extracted from the `eventInitDict data` member.

## Example

    var dataInit = {
      data : 'Some sample text'
    }

    var myPushEvent = new PushEvent('push', dataInit);

    myPushEvent.data.text(); // should return 'Some sample text'

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

`PushEvent`

42

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

37

No

No

42

44

48

Push enabled by default.

37

No

4.0

## See also

- [Push API](../push_api)
- [Service Worker API](../service_worker_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushEvent/PushEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushEvent/PushEvent</a>
