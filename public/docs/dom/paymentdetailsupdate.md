PaymentDetailsUpdate
====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Draft**

This page is not complete.

The `PaymentDetailsUpdate` dictionary is used to provide updated information to the payment user interface after it has been instantiated. This can be done either by calling the [`PaymentRequestUpdateEvent.updateWith()`](paymentrequestupdateevent/updatewith) method or by using the [`PaymentRequest.show()`](paymentrequest/show) method's `detailsPromise` parameter to provide a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that returns a `PaymentDetailsUpdate` that updates the payment information before the user interface is even enabled for the first time.

Properties
----------

*The `PaymentDetailsUpdate` dictionary is based on the [`PaymentDetailsBase`](paymentdetailsbase) dictionary, and inherits its properties, **which are included in the list below**.*

 <span class="page-not-created">`displayItems`</span> <span class="badge inline optional">Optional</span>   
An array of [`PaymentItem`](paymentitem) objects, each describing one line item for the payment request. These represent the line items on a receipt or invoice.

 [`error`](paymentdetailsupdate/error) <span class="badge inline optional">Optional</span>   
A [`DOMString`](domstring) specifying an error message to present to the user*.* When calling <span class="page-not-created">`updateWith()`</span>, including `error` in the updated data causes the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) to display the text as a general error message. For address field specific errors, use `shippingAddressErrors`.

 <span class="page-not-created">`modifiers`</span> <span class="badge inline optional">Optional</span>   
An array of <span class="page-not-created">`PaymentDetailsModifier`</span> objects, each describing a modifier for particular payment method identifiers. For example, you can use one to adjust the total payment amount based on the selected payment method ("5% cash discount!").

 [`shippingAddressErrors`](paymentdetailsupdate/shippingaddresserrors) <span class="badge inline optional">Optional</span>   
An [`AddressErrors`](addresserrors) object which includes an error message for each property of the shipping address that could not be validated.

 <span class="page-not-created">`shippingOptions`</span> <span class="badge inline optional">Optional</span>   
An array of <span class="page-not-created">`PaymentShippingOption`</span> objects, each describing one available shipping option from which the user may choose.

 <span class="page-not-created">`total`</span> <span class="badge inline optional">Optional</span>   
A [`PaymentItem`](paymentitem) providing an updated total for the payment. Make sure this equals the sum of all of the items in `displayItems`. *This is not calculated automatically*. You must update this value yourself anytime the total amount due changes. This lets you have flexibility for how to handle things like tax, discounts, and other adjustments to the total price charged.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentdetailsupdate">Payment Request API<br />
<span class="small">The definition of 'PaymentDetailsUpdate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PaymentDetailsUpdate`

61

≤18

55

Available only in nightly builds.

No

No

?

No

53

55

Available only in nightly builds.

No

?

6.0

`error`

61

≤18

55

Available only in nightly builds.

No

No

?

No

60

55

Available only in nightly builds.

No

?

8.0

`shippingAddressErrors`

61

≤18

55

Available only in nightly builds.

No

No

?

No

60

55

Available only in nightly builds.

No

?

8.0

`total`

61

≤18

55

Available only in nightly builds.

No

No

?

No

60

55

Available only in nightly builds.

No

?

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentDetailsUpdate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentDetailsUpdate</a>
