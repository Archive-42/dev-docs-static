# BasicCardRequest

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `BasicCardRequest` dictionary is a JavaScript object-structure that can be used in the [Payment Request API](payment_request_api). The properties of `BasicCardRequest` are defined in the [Basic Card Payment spec](#specifications)).

## Properties

[`BasicCardRequest.supportedNetworks`](basiccardrequest/supportednetworks) <span class="badge inline optional">Optional</span> <span class="notecard inline secure">Secure context</span>  
An optional array of [`DOMString`](domstring)s representing the card networks that the retailer supports (e.g. "`amex"`, "`mastercard"`); see [Card network identifiers](#card_network_identifiers) for a complete list. If the property is missing, it implies that all networks are supported.

### Obsolete properties

These properties have been removed from the Payment Method: Basic Card specification and should no longer be used.

[`BasicCardRequest.supportedTypes`](basiccardrequest/supportedtypes) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline optional">Optional</span> <span class="notecard inline secure">Secure context</span>  
This obsolete property was used to provide an optional array of [`DOMString`](domstring)s representing the card types that the retailer supports (e.g. `credit`, `debit`, `prepaid`). If the property is missing, it implies that all the card types are supported. Instead of using this property, it is up to the server to check support for the card given the information coded into the account number.

## Card network identifiers

The W3C maintains an official list of [approved card network identifier strings](https://www.w3.org/Payments/card-network-ids), which may be used in the [`supportedNetworks`](basiccardrequest/supportednetworks) list. Those are:

- `amex`
- `cartebancaire`
- `diners`
- `discover`
- `jcb`
- `mastercard`
- `mir`
- `unionpay`
- `visa`

## Examples

In the following example, the [`PaymentRequest()`](paymentrequest/paymentrequest) constructor is used to create a new payment request, which takes three objects as parameters — one containing details of the payment methods that can be used for the payment, one containing details of the actual order (such as items bought and shipping options), and an optional object that describes what data is needed to fullfil the payment (e.g., a shipping address).

The first of these three (`supportedInstruments` in the example below) contains a `data` property that has to conform to the structure defined by the `BasicCardRequest` dictionary.

    var supportedInstruments = [{
      supportedMethods: 'basic-card',
      data: {
        supportedNetworks: ['visa', 'mastercard', 'amex', 'jcb',
                            'diners', 'discover', 'mir', 'unionpay']
      }
    }];

    var details = {
      total: {label: 'Donation', amount: {currency: 'USD', value: '65.00'}},
      displayItems: [
        {
          label: 'Original donation amount',
          amount: {currency: 'USD', value: '65.00'}
        }
      ],
      shippingOptions: [
        {
          id: 'standard',
          label: 'Standard shipping',
          amount: {currency: 'USD', value: '0.00'},
          selected: true
        }
      ]
    };

    var options = {requestShipping: true};

    try {
      var request = new PaymentRequest(supportedInstruments, details, options);
      // Add event listeners here.
      // Call show() to trigger the browser's payment flow.
      request.show().then(function(instrumentResponse) {
        // Do something with the response from the UI.
      })
      .catch(function(err) {
        // Do something with the error from request.show().
      });
    } catch (e) {
      // Catch any other errors.
    }

Once the payment flow has been triggered using [`PaymentRequest.show()`](paymentrequest/show) and the promise resolves successfully, the [`PaymentResponse`](paymentresponse) object available inside the fulfilled promise (`instrumentResponse` above) will have a <span class="page-not-created">`PaymentResponse.details`</span> property that will contain response details. This has to conform to the structure defined by the [`BasicCardResponse`](basiccardresponse) dictionary, and may look something like this:

    {
      "cardNumber' : '9999999999999999",
      "cardholderName' : 'Mr Dick Straw",
      "cardSecurityCode" : "999",
      "expiryMonth" : "07",
      "expiryYear" : "2021",
      "billingAddress" : {
        "country" : "GB",
        // etc. billing address is a PaymentAddress object
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-method-basic-card/#basiccardrequest-dictionary">Basic Card Payment<br />
<span class="small">The definition of 'BasicCardRequest' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BasicCardRequest`

No

≤18-79

56

Available only in nightly builds.

No

No

No

No

57

56

Available only in nightly builds.

No

No

7.0

`supportedNetworks`

No

≤18-79

56

Available only in nightly builds.

No

No

No

No

57

56

Available only in nightly builds.

No

No

7.0

`supportedTypes`

No

≤18-79

56-65

It's now up to the payment processor to determine the type of card used, when necessary. Available only in nightly builds.

No

No

No

No

57

56-65

It's now up to the payment processor to determine the type of card used, when necessary. Available only in nightly builds.

No

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BasicCardRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BasicCardRequest</a>
