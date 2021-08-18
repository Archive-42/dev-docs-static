# PaymentResponse.shippingAddress

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `shippingAddress` read-only property of the `PaymentRequest` interface returns a [`PaymentAddress`](../paymentaddress) object containing the shipping address provided by the user.

## Syntax

    var shippingAddress = PaymentRequest.shippingAddress;

### Value

A [`PaymentAddress`](../paymentaddress) object providing details comprising the shipping address provided by the user.

## Example

Generally, the user agent will fill the `shippingAddress` property for you. You can trigger this by setting `PaymentOptions.requestShipping` to `true` when calling the [`PaymentRequest`](../paymentrequest/paymentrequest) constructor.

In the example below, the cost of shipping varies by geography. When the [`PaymentRequest.onshippingaddresschange`](../paymentrequest/onshippingaddresschange) is called, `updateDetails()` is called to update the details of the `PaymentRequest`, using `shippingAddress` to set the correct shipping cost.

    // Initialization of PaymentRequest arguments are excerpted for brevity.

    var payment = new PaymentRequest(supportedInstruments, details, options);

    request.addEventListener('shippingaddresschange', function(evt) {
      evt.updateWith(new Promise(function(resolve) {
        updateDetails(details, request.shippingAddress, resolve);
      }));
    });

    payment.show().then(function(paymentResponse) {
      // Processing of paymentResponse exerpted for the same of brevity.
    }).catch(function(err) {
      console.error("Uh oh, something bad happened", err.message);
    });

    function updateDetails(details, shippingAddress, resolve) {
      if (shippingAddress.country === 'US') {
        var shippingOption = {
          id: '',
          label: '',
          amount: {currency: 'USD', value: '0.00'},
          selected: true
        };
        if (shippingAddress.region === 'MO') {
          shippingOption.id = 'mo';
          shippingOption.label = 'Free shipping in Missouri';
          details.total.amount.value = '55.00';
        } else {
          shippingOption.id = 'us';
          shippingOption.label = 'Standard shipping in US';
          shippingOption.amount.value = '5.00';
          details.total.amount.value = '60.00';
        }
        details.displayItems.splice(2, 1, shippingOption);
        details.shippingOptions = [shippingOption];
      } else {
        delete details.shippingOptions;
      }
      resolve(details);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/">Payment Request API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`shippingAddress`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/shippingAddress" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/shippingAddress</a>
