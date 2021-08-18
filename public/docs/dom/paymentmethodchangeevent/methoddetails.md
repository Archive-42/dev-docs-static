# PaymentMethodChangeEvent.methodDetails

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only `methodDetails` property of the [`PaymentMethodChangeEvent`](../paymentmethodchangeevent) interface is an object containing any data the payment handler may provide to describe the change the user has made to their payment method. The value is `null` if no details are available.

## Syntax

    details = paymentMethodChangeEvent.methodName;

### Value

An object containing any data needed to describe the changes made to the payment method. The contents vary depending on the actual payment method chosen, so you will need to refer to the [`methodName`](methodname) property first, then inerpret the `methodDetails` after that.

The default value is `null`, indicating that no additional details are available.

## Example

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

Note that the `methodDetails` property is being used by the `calculateDiscount()` function to compute any payment discount, then [`updateWith()`](../paymentrequestupdateevent/updatewith) is called to update the event with the computed update.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentmethodchangeevent-methoddetails">Payment Request API<br />
<span class="small">The definition of 'PaymentMethodChangeEvent.methodDetails' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`methodDetails`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentMethodChangeEvent/methodDetails" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentMethodChangeEvent/methodDetails</a>
