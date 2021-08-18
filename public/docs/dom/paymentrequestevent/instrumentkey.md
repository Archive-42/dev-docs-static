PaymentRequestEvent.instrumentKey
=================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `instrumentKey` read-only property of the [`PaymentRequestEvent`](../paymentrequestevent) interface returns a <span class="page-not-created">`PaymentInstrument`</span> object reflecting the payment instrument selected by the user or an empty string if the user has not registered or chosen a payment instrument.

Syntax
------

    var instrumentKey = paymentRequestEvent.instrumentKey

### Value

A <span class="page-not-created">`PaymentInstrument`</span> object.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-handler/#instrumentkey-attribute">Payment Handler API<br />
<span class="small">The definition of 'instrumentKey' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`instrumentKey`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestEvent/instrumentKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestEvent/instrumentKey</a>
