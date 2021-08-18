# Client

The `Client` interface represents an executable context such as a [`Worker`](worker), or a [`SharedWorker`](sharedworker). [`Window`](window) clients are represented by the more-specific [`WindowClient`](windowclient). You can get `Client`/`WindowClient` objects from methods such as [`Clients.matchAll()`](clients/matchall) and [`Clients.get()`](clients/get).

## Methods

[`Client.postMessage()`](client/postmessage)  
Sends a message to the client.

## Properties

[`Client.id`](client/id) <span class="badge inline readonly">Read only </span>  
The universally unique identifier of the client as a string.

[`Client.type`](client/type) <span class="badge inline readonly">Read only </span>  
The client's type as a string. It can be "`window"`, "`worker"`, or "`sharedworker"`.

[`Client.url`](client/url) <span class="badge inline readonly">Read only </span>  
The URL of the client as a string.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#client">Service Workers<br />
<span class="small">The definition of 'Client' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Client`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`frameType`

43

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

30

11.1

43

43

44

30

11.3

4.0

`id`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`postMessage`

45

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

32

11.1

45

45

44

32

11.3

5.0

`type`

60

17

54

No

47

11.1

60

60

54

44

11.3

8.0

`url`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

## See also

- [Using Service Workers](service_worker_api/using_service_workers)
- [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
- [Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Client" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Client</a>
