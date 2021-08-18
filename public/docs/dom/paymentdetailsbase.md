# PaymentDetailsBase

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PaymentDetailsBase` dictionary is a mixin used by the <span class="page-not-created">`PaymentDetailsInit`</span> and [`PaymentDetailsUpdate`](paymentdetailsupdate) dictionaries. It is never directly used by developers and is included here only to be used as the basis for those documents.

## Properties

<span class="page-not-created">`displayItems`</span><span class="badge inline optional">Optional</span>  
An array of [`PaymentItem`](paymentitem) objects, each describing one line item for the payment request. These represent the line items on a receipt or invoice.

<span class="page-not-created">`modifiers`</span><span class="badge inline optional">Optional</span>  
An array of <span class="page-not-created">`PaymentDetailsModifier`</span> objects, each describing a modifier for particular payment method identifiers. For example, you can use one to adjust the total payment amount based on the selected payment method ("5% cash discount!").

<span class="page-not-created">`shippingOptions`</span><span class="badge inline optional">Optional</span>  
An array of <span class="page-not-created">`PaymentShippingOption`</span> objects, each describing one available shipping option from which the user may choose.

## Derived dictionaries

_The following dictionaries include `PaymentDetailsBase`._

<span class="page-not-created">`PaymentDetailsInit`</span>  
Provides payment information when calling the [`PaymentRequest()`](paymentrequest/paymentrequest) constructor.

[`PaymentDetailsUpdate`](paymentdetailsupdate)  
Provides updated payment details while the payment user interface is being handled. This can be delivered to the payment interface using either <span class="page-not-created">`PaymentDetailsUpdateEvent.updateWith()`</span> or by returning it from the optional `detailsUpdate` promise provided to the [`PaymentRequest.show()`](paymentrequest/show) call that begins the user interaction.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentdetailsbase">Payment Request API<br />
<span class="small">The definition of 'PaymentDetailsBase' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PaymentDetailsBase`

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

`displayItems`

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

`modifiers`

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

`shippingOptions`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentDetailsBase" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentDetailsBase</a>
