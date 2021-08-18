PaymentMethodChangeEvent.methodName
===================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only `methodName` property of the [`PaymentMethodChangeEvent`](../paymentmethodchangeevent) interface is a string which uniquely identifies the payment handler currently selected by the user. The payment handler may be a payment technology, such as Apple Pay or Android Pay, and each payment handler may support multiple payment methods; changes to the payment method within the payment handler are described by the `PaymentMethodChangeEvent`.

Syntax
------

    var methodName = paymentMethodChangeEvent.methodName;

### Value

A [`DOMString`](../domstring) which uniquely identifies the currently-selected payment handler. This may be a string chosen from the list of standardized payment method identifiers, or a URL used by the payment processing service. See [Payment method identifiers](#) in [Payment Request API](../payment_request_api) for more information.

The default value is the empty string, `""`.

Example
-------

This example uses the `paymentmethodchange` event to watch for changes to the payment method selected for Apple Pay, in order to compute a discount if the user chooses to use a Visa card as their payment method.

    request.onpaymentmethodchange = function(ev) {
      const { type: cardType } = ev.methodDetails;
      const newStuff = {};
      if (ev.methodName === "https://apple.com/apple-pay") {
        switch (cardType) {
          case "visa":
            // do Apple Pay specific handling for Visa card...
            // methodDetails contains the card information
            const result = calculateDiscount(ev.methodDetails);
            Object.assign(newStuff, result);
            break;
        }
      }
      // finally...
      ev.updateWith(newStuff);
    };
    const response = await request.show();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentmethodchangeevent-methodname">Payment Request API<br />
<span class="small">The definition of 'PaymentMethodChangeEvent.methodName' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`methodName`

76

79

No

No

63

12.1

No

76

No

54

12.2

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentMethodChangeEvent/methodName" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentMethodChangeEvent/methodName</a>
