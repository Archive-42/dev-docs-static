PaymentRequestEvent.respondWith()
=================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `respondWith` property of the [`PaymentRequestEvent`](../paymentrequestevent) interface prevents the default event handling and allows you to provide a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) for a [`PaymentResponse`](../paymentresponse) object yourself.

Syntax
------

    paymentRequestEvent.respondWith(
      // Promise that resolves with a PaymentResponse.
    )

### Parameters

promise  
A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`PaymentResponse`](../paymentresponse) object.

### Return value

A [`PaymentResponse`](../paymentresponse) object.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-handler/">Payment Handler API<br />
<span class="small">The definition of 'respondWith' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`respondWith`

70

79

No

No

57

No

No

70

No

49

No

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestEvent/respondWith" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestEvent/respondWith</a>
