ServiceWorker.scriptURL
=======================

Returns the `ServiceWorker` serialized script URL defined as part of [`ServiceWorkerRegistration`](../serviceworkerregistration). Must be on the same origin as the document that registers the `ServiceWorker`.

Syntax
------

    someURL = ServiceWorker.scriptURL

### Value

A [`USVString`](../usvstring) (see the [WebIDL definition of USVString](https://heycam.github.io/webidl/#idl-USVString).)

Examples
--------

    TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#service-worker-url">Service Workers<br />
<span class="small">The definition of 'scriptURL' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`scriptURL`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker/scriptURL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker/scriptURL</a>
