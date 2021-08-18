PaymentRequest: shippingoptionchange event
==========================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

For payment requests that request shipping information, and for which shipping options are offered, the `shippingoptionchange` event is sent to the [`PaymentRequest`](../paymentrequest) whenever the user chooses a shipping option from the list of available options. The string identifying the currently-selected shipping option can be found in the [`shippingOption`](shippingoption) property.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../paymentrequestupdateevent"><code>PaymentRequestUpdateEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onshippingoptionchange"><code>onshippingoptionchange</code></a></td></tr></tbody></table>

Examples
--------

This code snippet sets up a handler for the `shippingoptionchange` event. The code recalculates the total charge for the payment based on the selected shipping option. For example, if there are three options (such as "Free ground shipping", "2-day air", and "Next day"), each time the user chooses one of those options, this event handler is called to recalculate the total based on the changed shipping option.

    paymentRequest.addEventListener("shippingoptionchange", event => {
      const value = calculateNewTotal(paymentRequest.shippingOption);
      const total = {
        currency: "EUR",
        label: "Total due",
        value,
      };
      event.updateWith({ total });
    }, false);

After caling a custom function, `calculateNewTotal()`, to compute the updated total based on the newly-selected shipping option as specified by the [`shippingOption`](shippingoption). The revised total is submitted back to the payment request by calling the event's [`updateWith()`](../paymentrequestupdateevent/updatewith) method.

You can also create an event handler for `shippingoptionchange` using its corresponding event handler property, <span class="page-not-created">`onshippingoptionchange`</span>:

    paymentRequest.onshippingoptionchange = event => {
      const value = calculateNewTotal(paymentRequest.shippingOption);
      const total = {
        currency: "EUR",
        label: "Total due",
        value,
      };
      event.updateWith({ total });
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dfn-shippingoptionchange">Payment Request API<br />
<span class="small">The definition of 'shippingoptionchange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

BCD tables only load in the browser

-   [`onshippingoptionchange`](onshippingoptionchange) event handler property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/shippingoptionchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/shippingoptionchange_event</a>
