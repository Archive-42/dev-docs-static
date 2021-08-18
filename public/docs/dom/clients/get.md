# Clients.get()

The ` get``() ` method of the [`Clients`](../clients) interface gets a service worker client matching a given `id` and returns it in a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Syntax

    self.clients.get(id).then(function(client) {
      // do something with your returned client
    });

### Parameters

`id`  
A [`DOMString`](../domstring) representing the id of the client you want to get.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`Client`](../client) object or `undefined`.

## Examples

    self.clients.get(id).then(function(client) {
      self.clients.openWindow(client.url);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-clients-get">Service Workers<br />
<span class="small">The definition of 'get()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

51

17

45

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

38

11.1

No

51

45

41

11.3

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Clients/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Clients/get</a>
