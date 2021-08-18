PaymentRequest: paymentmethodchange event
=========================================

`paymentmethodchange` events are delivered by the [Payment Request API](../payment_request_api) to a [`PaymentRequest`](../paymentrequest) object when the user changes payment methods within a given payment handler. For example, if the user switches from one credit card to another on their [Apple Pay](https://www.apple.com/apple-pay/) account, a `paymentmethodchange` event is fired to let you know about the change.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../paymentmethodchangeevent"><code>PaymentMethodChangeEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onpaymentmethodchange"><code>onpaymentmethodchange</code></a></td></tr></tbody></table>

Examples
--------

Let's take a look at an example. This code creates a new [`PaymentRequest`](../paymentrequest), adds a handler for the `paymentmethodchange` event by calling the request's [`addEventListener()`](../eventtarget/addeventlistener), then calls [`show()`](show) to present the payment interface to the user.

The code assumes the existence of a method `detailsForShipping()`, which returns a [`PaymentDetailsUpdate`](../paymentdetailsupdate) object containing the shipping options for the `ground` shipping method, in the form found in the <span class="page-not-created">`PaymentShippingOption`</span> dictionary. By doing so, the payment form defaults to the ground shipping method.

    const options = {
      requestShipping: true
    };

    const paymentRequest = new PaymentRequest(paymentMethods,
          detailsForShipping("ground"), options);

    paymentRequest.addEventListener("paymentmethodchange", handlePaymentChange, false);

    paymentRequest.show()
    .then(response => response.complete("success"))
    .catch(err => console.log("Error handling payment request: " + err));

The event handler function itself, `handlePaymentChange()`, looks like this:

    handlePaymentChange = event => {
      const detailsUpdate = {};

      if (event.methodName === "https://apple.com/apple-pay") {
        const serviceFeeInfo = calculateServiceFee(event.methodDetails);
        Object.assign(detailsUpdate, serviceFeeInfo);
      }

      event.updateWith(detailsUpdate);
    }, false);

This begins by looking at the event's [`methodName`](../paymentmethodchangeevent/methodname) property; if that indicates that the user is trying to use Apple Pay, we pass the [`methodDetails`](../paymentmethodchangeevent/methoddetails) into a function called `calculateServiceFee()`, which we might create to take the information about the transaction, such as the underlying credit card being used to service the Apple Pay request, and compute and return an [`PaymentDetailsUpdate`](../paymentdetailsupdate) object that specifies changes to be applied to the [`PaymentRequest`](../paymentrequest) in order to add any service fees that the payment method might require.

Before the event handler returns, it calls the event's <span class="page-not-created">`PaymentMethodChangeEvent.updateWith()`</span> method to integrate the changes into the request.

Related events
--------------

-   `merchantvalidation`, `shippingaddresschange`, `shippingoptionchange`, and `payerdetailchange`

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dfn-paymentmethodchange">Payment Request API<br />
<span class="small">The definition of 'paymentmethodchange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`paymentmethodchange_event`

No

No

No

Available only in nightly builds.

No

No

No

No

No

No

Available only in nightly builds.

No

No

No

See also
--------

-   [Payment Request API](../payment_request_api)
-   [Using the Payment Request API](../payment_request_api/using_the_payment_request_api)
-   [`onpaymentmethodchange`](onpaymentmethodchange) event handler property
-   Related events: `merchantvalidation`, `payerdetailchange`, `shippingaddresschange`, `shippingoptionchange`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/paymentmethodchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/paymentmethodchange_event</a>
