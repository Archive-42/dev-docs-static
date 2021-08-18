# FetchEvent()

The `FetchEvent()` constructor creates a new [`FetchEvent`](../fetchevent) object.

## Syntax

    var fetchEvent = new FetchEvent(type, init);

### Parameters

`type`  
A [`DOMString`](../domstring) object specifying which event the object represents. This is always `fetch` for Fetch events.

`init` <span class="badge inline optional">Optional</span>  
An object conforming to the <span class="page-not-created">`FetchEventInit`</span> dictionary, containing options to apply to the event object. Options are as follows:

`clientId` <span class="badge inline readonly">Read only </span>  
The [`Client`](../client) that the current service worker is controlling.

`isReload` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that signifies whether the page was reloaded or not when the event was dispatched. `true` if yes, and `false` if not. Typically, pressing the refresh button in a browser is a reload, while clicking a link and pressing the back button is not. If not present, it defaults to `false`.

`preloadResponse` <span class="badge inline readonly">Read only </span>  
A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which returns a previously-loaded response to the client.

`replacesClientId` <span class="badge inline readonly">Read only </span>  
A [`DOMString`](../domstring) which identifies the client which is being replaced by `resultingClientId`.

`resultingClientId` <span class="badge inline readonly">Read only </span>  
A [`DOMString`](../domstring) containing the new `clientId` if the client changes as a result of the page load.

`request` <span class="badge inline readonly">Read only </span>  
The [`Request`](../request) object that would have triggered the event handler.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-fetchevent-fetchevent">Service Workers<br />
<span class="small">The definition of 'FetchEvent() constructor' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`FetchEvent`

40

≤18

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

No

40

40

44

27

No

4.0

## See also

- [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- [Fetch API](../fetch_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/FetchEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/FetchEvent</a>
