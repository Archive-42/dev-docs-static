PaymentRequestEvent.methodData
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `methodData` read-only property of the [`PaymentRequestEvent`](../paymentrequestevent) interface returns an array of <span class="page-not-created">`PaymentMethodData`</span> objects containing payment method identifers for the payment methods that the web site accepts and any associated payment method specific data.

Syntax
------

    var methodData[] = paymentRequestEvent.methodData

### Value

An array of <span class="page-not-created">`PaymentMethodData`</span> objects.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-handler/#methoddata-attribute">Payment Handler API<br />
<span class="small">The definition of 'methodData' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`methodData`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestEvent/methodData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestEvent/methodData</a>
