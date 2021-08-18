PaymentRequestUpdateEvent
=========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PaymentRequestUpdateEvent` interface is used for events sent to a [`PaymentRequest`](paymentrequest) instance when changes are made to shipping-related information for a pending [`PaymentRequest`](paymentrequest). Those events are:

 [`shippingaddresschange`](paymentrequest/shippingaddresschange_event) <span class="notecard inline secure">Secure context</span>   
Dispatched whenever the user changes their shipping address.  
Also available using the [`onshippingaddresschange`](paymentrequest/onshippingaddresschange) event handler property.

 [`shippingoptionchange`](paymentrequest/shippingoptionchange_event) <span class="notecard inline secure">Secure context</span>   
Dispatched whenever the user changes a shipping option.  
Also available using the [`onshippingoptionchange`](paymentrequest/onshippingoptionchange) event handler property.

Constructor
-----------

 [`PaymentRequestUpdateEvent()`](paymentrequestupdateevent/paymentrequestupdateevent) <span class="notecard inline secure">Secure context</span>   
Creates a new `PaymentRequestUpdateEvent` object.

Properties
----------

*Provides only the properties inherited from its parent interface, [`Event`](event).*

Methods
-------

*In addition to methods inherited from the parent interface, [`Event`](event), `PaymentRequestUpdateEvent` offers the following methods:*

 [`PaymentRequestUpdateEvent.updateWith()`](paymentrequestupdateevent/updatewith) <span class="notecard inline secure">Secure context</span>   
If the event handler determines that information included in the payment request needs to be changed, or that new information needs to be added, it calls `updateWith()` with the information that needs to be replaced or added.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#paymentrequestupdateevent-interface">Payment Request API<br />
<span class="small">The definition of 'PaymentRequestUpdateEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

BCD tables only load in the browser

-   [Using the Payment Request API](payment_request_api/using_the_payment_request_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestUpdateEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestUpdateEvent</a>
