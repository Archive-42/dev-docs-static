# PaymentResponse.shippingOption

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `shippingOption` read-only property of the `PaymentRequest` interface returns the ID attribute of the shipping option selected by the user. This option is only present when the `requestShipping` option is set to `true` in the <span class="page-not-created">`PaymentOptions`</span> object passed to the [`PaymentRequest`](../paymentrequest/paymentrequest) constructor.

## Syntax

    var shippingOption = PaymentRequest.shippingOption;

## Example

In the example below, the <span class="page-not-created">`PaymentRequest.onshippingaoptionchange`</span> event is called. It calls `updateDetails()` to toggle the shipping method between "standard" and "express".

    // Initialization of PaymentRequest arguments are excerpted for brevity.
    var payment = new PaymentRequest(supportedInstruments, details, options);

    request.addEventListener('shippingoptionchange', function(evt) {
      evt.updateWith(new Promise(function(resolve, reject) {
        updateDetails(details, request.shippingOption, resolve, reject);
      }));
    });

    payment.show().then(function(paymentResponse) {
      // Processing of paymentResponse exerpted for the same of brevity.
    }).catch(function(err) {
      console.error("Uh oh, something bad happened", err.message);
    });

    function updateDetails(details, shippingOption, resolve, reject) {
      var selectedShippingOption;
      var otherShippingOption;
      if (shippingOption === 'standard') {
        selectedShippingOption = details.shippingOptions[0];
        otherShippingOption = details.shippingOptions[1];
        details.total.amount.value = '55.00';
      } else if (shippingOption === 'express') {
        selectedShippingOption = details.shippingOptions[1];
        otherShippingOption = details.shippingOptions[0];
        details.total.amount.value = '67.00';
      } else {
        reject('Unknown shipping option \'' + shippingOption + '\'');
        return;
      }
      selectedShippingOption.selected = true;
      otherShippingOption.selected = false;
      details.displayItems.splice(2, 1, selectedShippingOption);
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

`shippingOption`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/shippingOption" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/shippingOption</a>
