PaymentRequest.canMakePayment()
===============================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`PaymentRequest`](../paymentrequest) method `canMakePayment()` determines whether or not the request is configured in a way that is compatible with at least one payment method supported by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent). You can call this before calling [`show()`](show) to provide a streamlined user experience when the user's browser can't handle any of the payment methods you accept.

For instance, you might call `canMakePayment()` to determine if the browser will let the user pay using Payment Request API, and if it won't, you could fall back to another payment method, or offer a list of methods that aren't handled by Payment Request API (or even provide instructions for paying by mail or by phone).

Syntax
------

    paymentRequest.canMakePayment()
        .then( canPay => { ... })
        .catch( error => { ... })

    canPay = await paymentRequest.canMakePayment();

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that resolves to `true` if the user agent supports any of the payment methods supplied when instantiating the request using the [`PaymentRequest`](paymentrequest) constructor. If the payment can't be processed, the promise receives a value of `false`.

**Note:** If you call this too often, the browser may reject the returned promise with a `DOMException`.

### Parameters

None

Examples
--------

In the following example, is [excerpted from a demo](https://rsolomakhin.github.io/samples/paymentrequest/can-make-payment/) that asynchronously builds a `PaymentRequest` object for both Apple Pay and credit cards. It wraps the call to `canMakePayment()` in feature detection, and calls an appropriate callback depending on the resolution of the `Promise`.

    async function initPaymentRquest() {
      const details = {
        total: {
          label: "Total",
          amount: {
            currency: "USD",
            value: "0.00",
          },
        },
      };

      const supportsApplePay = new PaymentRequest(
        [{ supportedMethods: "https://apple.com/apple-pay" }],
        details
      ).canMakePayment();

      // Supports Apple Pay?
      if (await supportsApplePay) {
        // show Apple Pay logo, for instance
        return;
      }

      // Otherwise... let's see if we can use basic card
      const supportsBasicCard = await new PaymentRequest(
        [{ supportedMethods: "basic-card" }],
        details
      ).canMakePayment();

      if (supportsBasicCard) {
        // show basic card support
        return;
      }

      // Otherwise, make payments using HTML form element
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#canmakepayment-method">Payment Request API<br />
<span class="small">The definition of 'canMakePayment()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`canMakePayment`

60

16

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

See also
--------

-   [`PaymentRequest.show()`](show)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/canMakePayment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/canMakePayment</a>
