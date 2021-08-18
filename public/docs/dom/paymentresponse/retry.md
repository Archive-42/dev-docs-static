PaymentResponse.retry()
=======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`PaymentResponse`](../paymentresponse) interface's `retry()` method makes it possible to ask the user to retry a payment after an error occurs during processing. This lets your app gracefully deal with situations such as invalid shipping addresses or declined credit cards.

Syntax
------

    retryPromise = paymentRequest.retry(errorFields);

### Parameters

`errorFields`  
A [`PaymentValidationErrors`](../paymentvalidationerrors) object, with the following properties:

 <span class="page-not-created">`error`</span> <span class="badge inline optional">Optional</span>   
A general description of a payment error from which the user may attempt to recover by retrying the payment, possibly after correcting mistakes in the payment information. `error` can be provided all by itself to provide only a generic error message, or in concert with the other properties to serve as an overview while other properties' values gude the user to errors in specific fields in the payment form.

 <span class="page-not-created">`payer`</span> <span class="badge inline optional">Optional</span>   
A [`PayerErrors`](../payererrors) compliant object which provides appropriate error messages for any of the fields describing the payer which failed validation.

 <span class="page-not-created">`paymentMethod`</span> <span class="badge inline optional">Optional</span>   
Any payment method specific errors which may have occurred. This object's contents will vary depending on the payment used. For example, if the user chose to pay by credit card using the `basic-card` payment method, this is a <span class="page-not-created">`BasicCardErrors`</span> object.

 <span class="page-not-created">`shippingAddress`</span> <span class="badge inline optional">Optional</span>   
An [`AddressErrors`](../addresserrors) object which contains error messages for any of the fields in the shipping address that failed validation.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is resolved when the payment is successfully completed. The promise is rejected with an appropriate exception value if the payment fails again.

Typically you will use this by calling [`show()`](../paymentrequest/show), then entering a loop or recursive function that checks the [`PaymentResponse`](../paymentresponse) for errors or other reasons to retry the payment request. If a retry is needed, the loop calls `retry()`, then loops back to check the response when it comes in. The loop exits only when the user either cancels the payment request or the request is successful.

See the [example](#examples) below for a thorough example, but the basic concept, in outline form, is:

1.  Create a new [`PaymentRequest`](../paymentrequest) (`new `[`PaymentRequest()`](../paymentrequest/paymentrequest))
2.  Display the payment request ([`PaymentRequest.show()`](../paymentrequest/show)
3.  If `show()` resolves, the returned [`PaymentResponse`](../paymentresponse) describes the requested payment and the options chosen by the user. Continue by...
    1.  Validate the returned response; if there are any fields whose values are not acceptable, call the response's [`complete()`](complete) method with a value of `"fail"` to indicate failure.
    2.  If the response's data is valid and acceptable, call `complete("success")` to finalize the payment and proces it.
4.  If `show()` is rejected, the payment request failed, usually because either there's already one being processed, because the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) doesn't support any of the specified payment methods, or because of a security issue. See the [list of exceptions](../paymentrequest/show#exceptions) for `show()` for further details. Call `complete("fail")` to close the payment request.

<!-- -->

    async function handlePayment() {
      const payRequest = new PaymentRequest(methodData, details, options);

      try {
        let payResponse = await payRequest.show();

        while (payResponse has errors) {
          /* let the user edit the payment information,
             wait until they submit */
          await response.retry();
        }
        await payResponse.complete("success");
      } catch(err) {
        /* handle the exception */
      }
    }

Examples
--------

<span class="underline">**try { await paymentRequest.retry(errorFields); } catch (DOMException err) { ... }**</span>

    async function doPaymentRequest() {
      const request = new PaymentRequest(methodData, details, options);
      const response = await request.show();
      await recursiveValidate(request, response);
      await response.complete("success");
    }

    // Keep validating until the data looks good!
    async function recursiveValidate(request, response) {
      const promisesToFixThings = [];
      const errors = await validate(request, response);
      if (!errors) {
        return;
      }
      if (errors.shippingAddress) {
        // "shippingaddresschange" fired at request object
        const promise = fixField(request, "shippingaddresschange", shippingValidator);
        promisesToFixThings.push(promise);
      }
      if (errors.payer) {
        // "payerdetailchange" fired at response object
        const promise = fixField(response, "payerdetailchange", payerValidator);
        promisesToFixThings.push(promise);
      }
      await Promise.all([response.retry(errors), ...promisesToFixThings]);
      await recursiveValidate(request, response);
    }

    function fixField(requestOrResponse, event, validator) {
      return new Promise(resolve => {
        // Browser keeps calling this until promise resolves.
        requestOrResponse.addEventListener(event, async function listener(ev) {
          const promiseToValidate = validator(requestOrResponse);
          ev.updateWith(promiseToValidate);
          const errors = await promiseToValidate;
          if (!errors) { // yay! fixed!
            event.removeEventListener(event, listener);
            resolve();
          }
        });
      });
    }

    doPaymentRequest();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentresponse-retry">Payment Request API<br />
<span class="small">The definition of 'retry()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`retry`

78

79

No

Available only in nightly builds.

No

47

12.1

No

78

No

Available only in nightly builds.

43

11.3

10.0

See also
--------

-   [`PaymentResponse`](../paymentresponse) interface.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/retry" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/retry</a>
