# PaymentRequest.onpaymentmethodchange

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`PaymentRequest`](../paymentrequest) event handler `onpaymentmethodchange` is invoked when the `paymentmethodchange` is fired, indicating that the user has changed payment methods within a given payment handler. For example, when using Apple Pay, the user can swipe to select different credit cards, debit cards, and so forth. Each time the user does so, this event is fired.

This event may not be fired by all payment handlers.

## Syntax

    PaymentRequest.addEventListener('paymentmethodchange', paymentMethodChangeEvent => { ... });

    PaymentRequest.onpaymentmethodchange = function(paymentMethodChangeEvent) { ... };

### Value

An event handler function which is to be called whenever the `paymentmethodchange` event is fired at the [`PaymentRequest`](../paymentrequest), indicating that the user has changed payment methods within the same payment handler.

The `paymentmethodchange` event is triggered by a user-agent controlled interaction (i.e., the end-user switches from a debit to a credit card in the payment UI). To make sure you receive the event, you should add event listeners to [`PaymentRequest`](../paymentrequest) object after instantiation, but before you call `show()`.

## Examples

An example payment method change handler is shown below; this example handles changes made to the payment method when using Apple Pay, specifically:

    request.onpaymentmethodchange = ev => {
      const { type: cardType } = ev.methodDetails;
      const newStuff = {};
      if (ev.methodName === "https://apple.com/apple-pay") {
        switch (cardType) {
          case "store":
            // do Apple Pay specific handling for store card...
            // methodDetails contains the store card information
            const result = calculateDiscount(ev.methodDetails);
            Object.assign(newStuff, result);
            break;
        }
      }
      // finally...
      ev.updateWith(newStuff);
    };
    const response = await request.show();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#onpaymentmethodchange-attribute">Payment Request API<br />
<span class="small">The definition of 'onpaymentmethodchange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onpaymentmethodchange`

76

79

No

Available only in nightly builds.

No

47

12.1

No

Yes

No

Available only in nightly builds.

44

12.2

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/onpaymentmethodchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/onpaymentmethodchange</a>
