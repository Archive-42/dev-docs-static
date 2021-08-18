# PaymentRequest.abort()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PaymentRequest.abort()` method of the [`PaymentRequest`](../paymentrequest) interface causes the user agent to end the payment request and to remove any user interface that might be shown.

## Syntax

    PaymentRequest.abort();

### Returns

Void.

### Parameters

None

## Examples

The following example sets up a timeout to clear the payment request that might have been abandoned or neglected.

    var request = new PaymentRequest(supportedInstruments, details, options);

    var paymentTimeout = window.setTimeout(() => {
      window.clearTimeout(paymentTimeout);
      request.abort().then(() => {
        print('Payment timed out after 20 minutes.');
      }).catch(() => {
        print('Unable to abort, because the user is currently in the process ' +
              'of paying.');
      });
    }, 20 * 60 * 1000);  /* 20 minutes */

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentrequest-abort">Payment Request API<br />
<span class="small">The definition of 'abort()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`abort`

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

## See also

- [`PaymentRequest.abort()`](abort)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/abort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/abort</a>
