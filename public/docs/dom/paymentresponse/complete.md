# PaymentResponse.complete()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`PaymentRequest`](../paymentrequest) method `complete()` of the [Payment Request API](../payment_request_api) notifies the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) that the user interaction is over, and causes any remaining user interface to be closed. This method must be called after the user accepts the payment request and the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by the [`PaymentRequest.show()`](../paymentrequest/show) method is resolved.

## Syntax

    completePromise = paymentRequest.complete(result);

### Parameters

`result` <span class="badge inline optional">Optional</span>  
A [`DOMString`](../domstring) indicating the state of the payment operation upon completion. It must be one of the following:

`success`  
The payment was successfully processed. The user agent may or may not present some form of "payment successful" indication to the user.

`fail`  
The payment was not successfully processed. The failure may or may not be announced to the user by the user agent, depending on its design.

`unknown`  
The success or failure status of the transaction is unknown or irrelevant, and the user agent should not present any notification, even if it normally would. _This is the default value._

**Note:** In older versions of the specification, an empty string, `""`, was used instead of `unknown` to indicate a completion without a known result state. See the [Browser compatibility](#browser_compatibility) section below for details.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves with no input value once the payment interface has been fully closed. If an error occurs, the promise instead rejects, returning one of the exceptions listed below.

### Exceptions

`AbortError`  
The document in which the payment request is taking place became inactive while the user interface was shown.

`InvalidStateError`  
The payment has already completed, or `complete()` was called while a request to retry the payment is pending. You can't treat a payment as complete after requesting that the payment be tried again.

## Examples

The following example sends payment information to a secure server using the [Fetch API](../fetch_api). It calls `complete()` with an answer appropriate to the status in the response.

    // Initialization of PaymentRequest arguments are excerpted for the
    //   sake of brevity.
    var payment = new PaymentRequest(supportedInstruments, details, options);

    payment.show().then(function(paymentResponse) {
      var fetchOptions = {
        method: 'POST',
        credentials: include,
        body: JSON.stringify(paymentResponse)
      };
      var serverPaymentRequest = new Request('secure/payment/endpoint');
      fetch(serverPaymentRequest, fetchOptions).then( response => {
        if (response.status < 400) {
          paymentResponse.complete("success");
        } else {
          paymentResponse.complete("fail");
        };
      }).catch( reason => {
        paymentResponse.complete("fail");
      });
    }).catch(function(err) {
      console.error("Uh oh, something bad happened", err.message);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentresponse-complete">Payment Request API<br />
<span class="small">The definition of 'PaymentResponse: complete' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`complete`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/complete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/complete</a>
