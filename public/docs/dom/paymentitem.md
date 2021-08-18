# PaymentItem

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`PaymentItem`](paymentitem) dictionary is used by the [Payment Request API](payment_request_api) to describe a single line item on a payment request. This might be an item or service being purchased or a tax or other charge.

## Properties

<span class="page-not-created">`amount`</span> <span class="notecard inline secure">Secure context</span>  
A [`PaymentCurrencyAmount`](paymentcurrencyamount) object describing the monetary value of the item.

<span class="page-not-created">`label`</span> <span class="notecard inline secure">Secure context</span>  
A string specifying a human-readable name or description of the item or service being charged for. This may be displayed to the user by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent), depending on the design of the interface.

<span class="page-not-created">`pending`</span> <span class="notecard inline secure">Secure context</span>  
A Boolean value which is `true` if the specified `amount` has not yet been finalized. This can be used to show items such as shipping or tax amounts that depend upon the selection of shipping address, shipping option, or so forth. The user agent may show this information but is not required to do so.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentitem">Payment Request API<br />
<span class="small">The definition of 'PaymentItem' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PaymentItem`

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

No

`amount`

61

≤18

55

No

No

?

No

53

55

No

?

No

`label`

61

≤18

55

No

No

?

No

53

55

No

?

No

`pending`

61

≤18

55

No

No

?

No

53

55

No

?

No

## See also

- [Payment Request API](payment_request_api)
- [Using the Payment Request API](payment_request_api/using_the_payment_request_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentItem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentItem</a>
