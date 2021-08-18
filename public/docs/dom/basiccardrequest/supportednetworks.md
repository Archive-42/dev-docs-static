# BasicCardRequest.supportedNetworks

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `supportedNetworks` property of the [`BasicCardRequest`](../basiccardrequest) dictionary contains an array of [`DOMString`](../domstring)s representing the card networks that the retailer supports (e.g. `amex`, `mastercard`).

## Syntax

    supportedNetworks : [value [, ... value]]

### Value

An array containing one or more [`DOMString`](../domstring)s, which describe the card networks the retailer supports. Legal values are defined in the W3C's document [Card Network Identifiers Approved for use with Payment Request API](https://www.w3.org/Payments/card-network-ids), and are currently:

- `amex`
- `cartebancaire`
- `diners`
- `discover`
- `jcb`
- `mastercard`
- `mir`
- `unionpay`
- `visa`

## Example

The following example shows a sample definition of the first parameter of the [`PaymentRequest()`](../paymentrequest/paymentrequest) constructor, the `data` property of which contains `supportedNetworks` and `supportedTypes` properties.

    var supportedInstruments = [{
      supportedMethods: 'basic-card',
      data: {
        supportedNetworks: ['visa', 'mastercard', 'amex', 'jcb',
                            'diners', 'discover', 'mir', 'unionpay'],
        supportedTypes: ['credit', 'debit']
      }
    }];

    var details = { ... };

    var options = { ... };

    var request = new PaymentRequest(supportedInstruments, details, options);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-method-basic-card/#dom-basiccardrequest-supportednetworks">Basic Card Payment<br />
<span class="small">The definition of 'supportedNetworks' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BasicCardRequest/supportedNetworks" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BasicCardRequest/supportedNetworks</a>
