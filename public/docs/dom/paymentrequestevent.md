PaymentRequestEvent
===================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PaymentRequestEvent` interface of the [Payment Request API](payment_request_api) is the object passed to a payment handler when a [`PaymentRequest`](paymentrequest) is made.

Constructor
-----------

 [`PaymentRequestEvent()`](paymentrequestevent/paymentrequestevent)<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Creates a new `PaymentRequestEvent` object.

Properties
----------

 [`instrumentKey`](paymentrequestevent/instrumentkey)<span class="badge inline readonly">Read only </span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a <span class="page-not-created">`PaymentInstrument`</span> object reflecting the payment instrument selected by the user or an empty string if the user has not registered or chosen a payment instrument.

 [`methodData`](paymentrequestevent/methoddata)<span class="badge inline readonly">Read only </span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns an array of <span class="page-not-created">`PaymentMethodData`</span> objects containing payment method identifers for the payment methods that the web site accepts and any associated payment method specific data.

 [`modifiers`](paymentrequestevent/modifiers)<span class="badge inline readonly">Read only </span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns an array of objects containing changes to payment details.

 [`paymentRequestId`](paymentrequestevent/paymentrequestid)<span class="badge inline readonly">Read only </span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns the ID of the [`PaymentRequest`](paymentrequest) object.

 [`paymentRequestOrigin`](paymentrequestevent/paymentrequestorigin)<span class="badge inline readonly">Read only </span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns the origin where the [`PaymentRequest`](paymentrequest) object was initialized.

 [`topOrigin`](paymentrequestevent/toporigin)<span class="badge inline readonly">Read only </span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns the top-level origin where the [`PaymentRequest`](paymentrequest) object was initialized.

 [`total`](paymentrequestevent/total)<span class="badge inline readonly">Read only </span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns the total amount being requested for payment.

Methods
-------

 [`openWindow()`](paymentrequestevent/openwindow)<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Opens the specified URL in a new window, if and only if the given URL is on the same origin as the calling page. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a reference to a [`WindowClient`](windowclient).

 [`respondWith()`](paymentrequestevent/respondwith)<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Prevents the default event handling and allows you to provide a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) for a [`PaymentResponse`](paymentresponse) object yourself.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-handler/#the-paymentrequestevent">Payment Handler API<br />
<span class="small">The definition of 'PaymentRequestEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PaymentRequestEvent`

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

`PaymentRequestEvent`

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

`modifiers`

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

`openWindow`

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

`paymentRequestId`

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

`paymentRequestOrigin`

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

`topOrigin`

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

`total`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestEvent</a>
