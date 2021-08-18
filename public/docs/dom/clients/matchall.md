# Clients.matchAll()

The `matchAll()` method of the [`Clients`](../clients) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) for a list of service worker [`Client`](../client) objects. Include the `options` parameter to return all service worker clients whose origin is the same as the associated service worker's origin. If options are not included, the method returns only the service worker clients controlled by the service worker.

## Syntax

    self.clients.matchAll(options).then(function(clients) {
      // do something with your clients list
    });

### Parameters

`options` <span class="badge inline optional">Optional</span>  
An options object allowing you to set options for the matching operation. Available options are:

- `includeUncontrolled`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) — if set to `true`, the matching operation will return all service worker clients who share the same origin as the current service worker. Otherwise, it returns only the service worker clients controlled by the current service worker. The default is `false`.
- `type`: Sets the type of clients you want matched. Available values are `"window"`, `"worker"`, `"sharedworker"`, and `"all"`. The default is `"window"`.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an array of [`Client`](../client) objects. In Chrome 46/Firefox 54 and later, this method returns clients in most recently focused order, correct as per spec.

## Examples

    clients.matchAll(options).then(function(clientList) {
      for (var i = 0 ; i < clientList.length ; i++) {
        if (clientList[i].url === 'index.html') {
          clients.openWindow(clientList[i]);
          // or do something else involving the matching client
        }
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#clients-matchall">Service Workers<br />
<span class="small">The definition of 'Clients: matchall' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`matchAll`

47

`Client` objects returned in most recent focus order.

17

`Client` objects returned in most recent focus order.

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

54

`Client` objects returned in most recent focus order.

No

32

11.1

47

`Client` objects returned in most recent focus order.

47

`Client` objects returned in most recent focus order.

44

54

`Client` objects returned in most recent focus order.

32

11.3

4.0

`Client` objects returned in most recent focus order.

`includeUncontrolled_option`

47

`Client` objects returned in most recent focus order.

≤79

`Client` objects returned in most recent focus order.

45

`includeUncontrolled` support.

No

38

11.1

47

`Client` objects returned in most recent focus order.

47

`Client` objects returned in most recent focus order.

45

`includeUncontrolled` support.

41

11.3

5.0

`Client` objects returned in most recent focus order.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Clients/matchAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Clients/matchAll</a>
