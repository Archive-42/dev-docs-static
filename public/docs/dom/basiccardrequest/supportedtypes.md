# BasicCardRequest.supportedTypes

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete `supportedTypes` property of the [`BasicCardRequest`](../basiccardrequest) dictionary can optionally be provided to specify an array of [`DOMString`](../domstring)s representing the card types that the retailer supports (e.g. `credit`, `debit`, `prepaid`).

This property is obsolete and should no longer be used. Instead of making the web app or site worry about this, the onus has been transferred to the payment processor.

## Syntax

    basicCardRequest.supportedTypes = [cardType1...cardTypeN];

### Value

An array containing one or more [`DOMString`](../domstring)s, which describe the card types the retailer supports. Legal values are defined in `BasicCardType` enum, and are currently:

- `credit`
- `debit`
- `prepaid`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BasicCardRequest/supportedTypes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BasicCardRequest/supportedTypes</a>
