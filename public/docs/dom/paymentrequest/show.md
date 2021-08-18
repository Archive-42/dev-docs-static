PaymentRequest.show()
=====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The **[`PaymentRequest`](../paymentrequest)** interface's `show()` method instructs the user agent to begin the process of showing and handling the user interface for the payment request to the user.

For security reasons, the `PaymentRequest.show()` method can't just be initiated at any time. It may only be called while handling events that represent user interactions, such as `click`, `keyup`, or the like.

Only one payment request can be in the process of being handled at once, across all documents. Once one `PaymentRequest`'s `show()` method has been called, any other call to `show()` will by rejected with an `AbortError` until the returned promise has been concluded, either by being fulfilled with a [`PaymentResponse`](../paymentresponse) indicating the results of the payment request, or by being rejected with an error.

**Note:** In reality, despite the fact that the specification says this can't be done, some browsers, including Firefox, support multiple active payment requests at a time.

If your architecture doesn't necessarily have all of the data ready to go at the moment it instantiates the payment interface by calling `show()`, specify the `detailsPromise` parameter, providing a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that is fulfilled once the data is ready. If this is provided, `show()` will not allow the user to interact with the payment interface until the promise is fulfilled, so that data can be updated prior to the user engaging with the payment process.

Processing the result and, if necessary, calling [`PaymentResponse.retry()`](../paymentresponse/retry) to retry a failed payment can all be done either asynchronously or synchronously, depending on your needs. For the best user experience, asynchronous solutions are typically the best way to go. Most examples on MDN and elsewhere use `async`/`await` to wait asynchronously while results are validated and so forth.

Syntax
------

    paymentPromise = paymentRequest.show(detailsPromise);

### Parameters

 `detailsPromise` <span class="badge inline optional">Optional</span>   
An optional [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that you can provide if your architecture requires that the payment request's details need to be updated between instantiating the payment interface and the user beginning to interact with it. The promise should resolve with a [`PaymentDetailsUpdate`](../paymentdetailsupdate) object containing the updated information.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that eventually resolves with a [`PaymentResponse`](../paymentresponse). The promise is resolved when the user accepts the payment request (such as by clicking a "Pay" button in the browser's payment sheet).

### Exceptions

`AbortError`  
The returned promise rejects with an `AbortError` if the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) is already showing a payment panel. Only one payment panel may be visible at a time *across all documents loaded by the user agent*.

The promise is also rejected with `AbortError` if the user cancels the payment request.

`InvalidStateError`  
The promise rejects with an `InvalidStateError` if the same payment has already been shown for this request (its state is `interactive` because it is being shown already).

`NotSupportedError`  
The promise rejects with a `NotSupportedError` if the user agent does not support the payment methods specified when the [`PaymentRequest`](paymentrequest) constructor was called.

`SecurityError`  
The promise rejects with a `SecurityError` if the call to `show()` was not in response to a user action, such as a `click` or `keyup` event. Other reasons a `SecurityError` may be thrown are at the discretion of the user agent, and may include situations such as too many calls to `show()` being made in a short time or `show()` being called while payment requests are blocked by parental controls.

Usage notes
-----------

The most common patterns for using `show()` involve either the `async`/`await` syntax or the use of `show().then().catch()` to handle the response and any possible rejection. Those look like this:

### async/await syntax

Using `await` to wait for a promise to be resolved makes it possible to write the code to handle payments particularly cleanly:

    async function processPayment() {
      try {
        const payRequest = new PaymentRequest(methodData, details, options);

        payRequest.onshippingaddresschange = ev => ev.updateWith(checkAddress(payRequest));
        payRequest.onshippingoptionchange = ev => ev.updateWith(checkShipping(payRequest));

        const response = await payRequest.show();
        await validateResponse(response);
      } catch(err) {
        /* handle the error; AbortError usually means a user cancellation */
      }
    }

In this code, the methods `checkAddress()` and `checkShipping()`, respectively, check the shipping address and the shipping option changes and supply in response either a [`PaymentDetailsUpdate`](../paymentdetailsupdate) object or a promise to return one; this object contains the fields in the [`PaymentResponse`](../paymentresponse) which have been or need to be changed.

The `validateResponse()` method, below, is called once `show()` returns, in order to look at the returned `response` and either submit the payment or reject the payment as failed:

    async function validateResponse(response) {
      try {
        if (await checkAllValues(response)) {
          await response.complete("success");
        } else {
          await response.complete("fail");
        }
      } catch(err) {
        await response.complete("fail");
      }
    }

Here, a custom function called `checkAllValues()` looks at each value in the `response` and ensures that they're valid, returning `true` if every field is valid or `false` if any are not. If and only if every field is valid, the [`complete()`](../paymentresponse/complete) method is called on the response with the string `"success"`, which indicates that everything is valid and that the payment can complete accordingly.

If any fields have unacceptable values, or if an exception is thrown by the previous code, `complete()` is called with the string `"fail"`, which indicates that the payment process is complete and failed.

Instead of immediately failing, you could choose to call [`retry()`](../paymentresponse/retry) on the response object to ask the user agent to try to process the payment again; this should usually only be done after the user has made any needed corrections to the order.

Starting the payment process, in the end, is as simple as calling the `processPayment()` method.

### then/catch syntax

You can also use the older promise-based approach to work with payments, using the [`then()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then) and [`catch()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/catch) functions on the promise returned by `show()`:

    function processsPayment() {
      const payRequest = new PaymentRequest(methodData, details, options);

      payRequest.onshippingaddresschange = ev => ev.updateWith(checkAddress(payRequest));
      payRequest.onshippingoptionchange = ev => ev.updateWith(checkShipping(payRequest));

      payRequest.show()
        .then(response => validateResponse(response))
        .catch(err => handleError(err));
    }

This is functionally equivalent to the `processPayment()` method using the `await` syntax.

    function validateResponse(response) {
      checkAllValues(response)
        .then(response => response.complete("success"))
        .catch(response => response.complete("fail"));
    }

You could even have `checkAllValues()` be a synchronous function, although that may have performance implications you don't want to deal with:

    function validateResponse(response) {
      if (checkAllValues(response) {
        response.complete("success");
      } else {
        response.complete("fail");
      }
    }

See the article [Using promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises) for more information if you need more information about working with promises.

Examples
--------

In the following example, a `PaymentRequest` object is instantiated before the `show()` method is called. This method triggers the user agent's built-in process for retrieving payment information from the user. The `show()` method returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`PaymentResponse`](../paymentresponse) object when the user interaction is complete. The developer then uses the information in the `PaymentResponse` object to format and send payment data to the server. You should send the payment information to the server asynchronously so that the final call to [`paymentResponse.complete()`](../paymentresponse/complete) can indicate the success or failure of the payment.

    button.onclick = async function handlePurchase() {
      // Initialization of PaymentRequest arguments are excerpted for the sake of
      // brevity.
      const payment = new PaymentRequest(methods, details, options);
      try {
        const response = await payment.show();
        // Process response here, including sending payment instrument
        // (e.g., credit card) information to the server.
        // paymentResponse.methodName contains the selected payment method
        // paymentResponse.details contains a payment method specific response
        await response.complete("success");
      } catch (err) {
        console.error("Uh oh, something bad happened", err.message);
      }
    }

The following example shows how to update the payment sheet as it's being presented to the end-user.

    async function requestPayment() {
      // We start with AU$0 as the total.
      const initialDetails = {
        total: {
          label: "Total",
          amount: { value: "0", currency: "AUD" },
        },
      };
      const request = new PaymentRequest(methods, initialDetails, options);
      // Check if the user supports the `methods`
      if (!await request.canMakePayment()) {
        return; // no, so use a web form instead.
      }
      // Let's update the total as the sheet is shown
      const updatedDetails = {
        total: {
          label: "Total",
          amount: { value: "20", currency: "AUD" },
        },
      };
      const response = await request.show(updatedDetails);
      // Check response, etc...
    }

    document.getElementById("buyButton").onclick = requestPayment;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#show-method">Payment Request API<br />
<span class="small">The definition of 'show(optional detailsPromise)' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`show`

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

See also
--------

-   [Payment Request API](../payment_request_api)
-   [Using the Payment Request API](../payment_request_api/using_the_payment_request_api)
-   [`PaymentRequest.abort()`](abort)
-   <span class="page-not-created">`PaymentRequest.retry()`</span>
-   <span class="page-not-created">`PaymentRequest.complete()`</span>
-   [`PaymentResponse`](../paymentresponse)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/show" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/show</a>
