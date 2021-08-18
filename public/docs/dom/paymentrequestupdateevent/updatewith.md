# PaymentRequestUpdateEvent.updateWith()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `updateWith()` method of the [`PaymentRequestUpdateEvent`](../paymentrequestupdateevent) interface updates the details of an existing [`PaymentRequest`](../paymentrequest).

## Syntax

    paymentRequestUpdateEvent.updateWith(details);

### Parameters

`details`  
A [`PaymentDetailsUpdate`](../paymentdetailsupdate) object specifying the changes applied to the payment request:

<span class="page-not-created">`displayItems`</span> <span class="badge inline optional">Optional</span>  
An array of [`PaymentItem`](../paymentitem) objects, each describing one line item for the payment request. These represent the line items on a receipt or invoice.

[`error`](../paymentdetailsupdate/error) <span class="badge inline optional">Optional</span>  
A [`DOMString`](../domstring) specifying an error message to present to the user*.* When calling <span class="page-not-created">`updateWith()`</span>, including `error` in the updated data causes the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) to display the text as a general error message. For address field specific errors, use `shippingAddressErrors`.

<span class="page-not-created">`modifiers`</span> <span class="badge inline optional">Optional</span>  
An array of <span class="page-not-created">`PaymentDetailsModifier`</span> objects, each describing a modifier for particular payment method identifiers. For example, you can use one to adjust the total payment amount based on the selected payment method ("5% cash discount!").

[`shippingAddressErrors`](../paymentdetailsupdate/shippingaddresserrors) <span class="badge inline optional">Optional</span>  
An [`AddressErrors`](../addresserrors) object which includes an error message for each property of the shipping address that could not be validated.

<span class="page-not-created">`shippingOptions`</span> <span class="badge inline optional">Optional</span>  
An array of <span class="page-not-created">`PaymentShippingOption`</span> objects, each describing one available shipping option from which the user may choose.

<span class="page-not-created">`total`</span> <span class="badge inline optional">Optional</span>  
A [`PaymentItem`](../paymentitem) providing an updated total for the payment. Make sure this equals the sum of all of the items in `displayItems`. _This is not calculated automatically_. You must update this value yourself anytime the total amount due changes. This lets you have flexibility for how to handle things like tax, discounts, and other adjustments to the total price charged.

### Return value

`undefined`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#updatewith-method">Payment Request API<br />
<span class="small">The definition of 'PaymentRequestUpdateEvent.updateWith()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`updateWith`

60

15

No

Available only in nightly builds.

No

47

11.1

No

56

No

Available only in nightly builds.

43

11.3

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestUpdateEvent/updateWith" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestUpdateEvent/updateWith</a>
