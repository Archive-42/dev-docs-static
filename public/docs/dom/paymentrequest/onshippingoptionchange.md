PaymentRequest.onshippingoptionchange
=====================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `onshippingoptionchange` event of the [`PaymentRequest`](../paymentrequest) interface is fired whenever the user changes a shipping option.

Syntax
------

    PaymentRequest.addEventListener('shippingoptionchange', shippingOptionChangeEvent => { ... });

    PaymentRequest.onshippingoptionchange = function(shippingOptionChangeEvent) { ... };

Examples
--------

The `shippingoptionchange` event is triggered by a user-agent controlled interaction. If the option stored by the user agent changes at any time during a payment process, the event is triggered. To make sure an updated option is included when sending payment information to the server, you should add event listeners for a [`PaymentRequest`](../paymentrequest) object after instantiation, but before the call to `show()`.

    // Initialization of PaymentRequest arguments are excerpted for clarity.
    var request = new PaymentRequest(supportedInstruments, details, options);

    // When user selects a shipping address
    request.addEventListener('shippingaddresschange', e => {
      e.updateWith(((details, addr) => {
        var shippingOption = {
          id: '',
          label: '',
          amount: { currency: 'USD', value: '0.00' },
          selected: true
        };
        // Shipping to US is supported
        if (addr.country === 'US') {
          shippingOption.id = 'us';
          shippingOption.label = 'Standard shipping in US';
          shippingOption.amount.value = '0.00';
          details.total.amount.value = '55.00';
        // Shipping to JP is supported
        } else if (addr.country === 'JP') {
          shippingOption.id = 'jp';
          shippingOption.label = 'International shipping';
          shippingOption.amount.value = '10.00';
          details.total.amount.value = '65.00';
        // Shipping to elsewhere is unsupported
        } else {
          // Empty array indicates rejection of the address
          details.shippingOptions = [];
          return Promise.resolve(details);
          console.log(details.error);
        }
        // Hardcode for simplicity
        if (details.displayItems.length === 2) {
          details.displayItems[2] = shippingOption;
        } else {
          details.displayItems.push(shippingOption);
        }
        details.shippingOptions = [shippingOption];

        return Promise.resolve(details);
      })(details, request.shippingAddress));
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#onshippingoptionchange-attribute">Payment Request API<br />
<span class="small">The definition of 'onshippingoptionchange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onshippingoptionchange`

60

15

No

Available only in nightly builds.

No

47

11.1

No

53

No

Available only in nightly builds.

44

11.3

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/onshippingoptionchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/onshippingoptionchange</a>
