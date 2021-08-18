PaymentResponse: payerdetailchange event
========================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

`payerdetailchange` events are delivered by the [Payment Request API](../payment_request_api) to a [`PaymentResponse`](../paymentresponse) object when the user makes changes to their personal information while filling out a payment request form.

The event handler for `payerdetailchange` should check each value in the form that has changed and ensure that the values are valid. If any are invalid, appropriate error messages should be configured and the [`retry()`](retry) method should be called on the [`PaymentResponse`](../paymentresponse) to ask the user to update the invalid entries.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../paymentrequestupdateevent"><code>PaymentRequestUpdateEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onpayerdetailchange</code></td></tr></tbody></table>

Examples
--------

In the example below, `onpayerdetailchange` is used to set up a listener for the `payerdetailchange` event in order to validate the information entered by the user, requesting that any mistakes be corrected

    // Options for PaymentRequest(), indicating that shipping address,
    // payer email address, name, and phone number all be collected.

    const options = {
      requestShipping: true,
      requestPayerEmail: true,
      requestPayerName: true,
      requestPayerPhone: true,
    };
    const request = new PaymentRequest(methods, details, options);
    const response = request.show();

    // Get the data from the response

    let {
      payerName: oldPayerName,
      payerEmail: oldPayerEmail,
      payerPhone: oldPayerPhone,
    } = response;

    // Set up a handler for payerdetailchange events, to
    // request corrections as needed.

    response.onpayerdetailchange = async ev => {
      const promisesToValidate = [];
      const { payerName, payerEmail, payerPhone } = response;

      // Validate each value which changed by calling a function
      // that validates each type of data, returning a promise which
      // resolves if the data is valid.

      if (oldPayerName !== payerName) {
        promisesToValidate.push(validateName(payerName));
        oldPayerName = payerName;
      }
      if (oldPayerEmail !== payerEmail) {
        promisesToValidate.push(validateEmail(payerEmail));
        oldPayerEmail = payerEmail;
      }
      if (oldPayerPhone !== payerPhone) {
        promisesToValidate.push(validatePhone(payerPhone));
        oldPayerPhone = payerPhone;
      }

      // As each validation promise resolves, add the results of the
      // validation to the errors list

      const errors = await Promise.all(promisesToValidate).then(results =>
        results.reduce((errors, result), Object.assign(errors, result))
      );

      // If we found any errors, wait for them to be corrected

      if (Object.getOwnPropertyNames(errors).length) {
        await response.retry(errors);
      } else {
        // We have a good payment; send the data to the server
        await fetch("/pay-for-things/", { method: "POST", body: response.json() });
        response.complete("success");
      }
    };

    await response.retry({
      payer: {
        email: "invalid domain.",
        phone: "invalid number.",
      },
    });

### addEventListener equivalent

You could also set up the event handler using the `addEventListener()` method:

    response.addEventListener("payerdetailchange", async ev => {
      ...
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dfn-payerdetailchange">Payment Request API<br />
<span class="small">The definition of 'payerdetailchange event' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`payerdetailchange_event`

No

No

No

Available only in nightly builds.

No

No

?

No

No

No

Available only in nightly builds.

No

?

No

See also
--------

-   [Payment Request API](../payment_request_api)
-   [Using the Payment Request API](../payment_request_api/using_the_payment_request_api)
-   [`PaymentResponse`](../paymentresponse)
-   `payerdetailchange`
-   `paymentmethodchange`
-   `shippingaddresschange`
-   `shippingoptionchange`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/payerdetailchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/payerdetailchange_event</a>
