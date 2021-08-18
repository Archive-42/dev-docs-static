# PaymentRequest: shippingaddresschange event

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `shippingaddresschange` event is sent to the [`PaymentRequest`](../paymentrequest) object when the user selects a shipping address or changes details of their shipping address.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../paymentrequestupdateevent"><code>PaymentRequestUpdateEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onshippingaddresschange"><code>onshippingaddresschange</code></a></td></tr></tbody></table>

## Usage notes

Depending on the browser, the shipping address information may be redacted for privacy reasons. That is, the [`PaymentAddress`](../paymentaddress) which contains the shipping address may have some portions of its content altered, obscured, or left out entirely in order to prevent identifying the user without their consent (since if they choose to have you ship products to them, you'll need their address).

## Example

In this example, a handler for the `shippingaddresschange` event is set up to validate that the address meets requirements set by the web application.

    const paymentRequest = new PaymentRequest(methodData, details, options);

    paymentRequest.addEventListener("shippingaddresschange", event => {
      let detailsUpdate = checkAddress(paymentRequest.shippingAddress);
      event.updateWith(detailsUpdate);
    }, false);

    const checkAddress = theAddress => {
      let detailsUpdate = {};

      // Check the address, return a PaymentDetailsUpdate object
      // with any changes or errors.

      return detailsUpdate;
    };

You can also establish a handler for `shippingaddresschange` using the [`onshippingaddresschange`](onshippingaddresschange) event handler property:

    paymentRequest.onshippingaddresschange = event => {
      let detailsUpdate = checkAddress(paymentRequest.shippingAddress);
      event.updateWith(detailsUpdate);
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dfn-shippingaddresschange">Payment Request API<br />
<span class="small">The definition of 'shippingaddresschange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

BCD tables only load in the browser

- [`onshippingaddresschange`](onshippingaddresschange) event handler property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/shippingaddresschange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/shippingaddresschange_event</a>
