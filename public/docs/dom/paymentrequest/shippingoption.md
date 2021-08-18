# PaymentRequest.shippingOption

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `shippingOption` read-only attribute of the [`PaymentRequest`](../paymentrequest) interface returns either the id of a selected shipping option, null (if no shipping option was set to be selected) or a shipping option selected by the user. It is initially `null` by when no "selected" shipping options are provided.

This attribute is only populated if the constructor is called with the `requestShipping` flag set to `true`. If `requestShipping` was `false` (or missing), `shippingOption` returns `null`, even the developer provides a selected a shipping option.

## Syntax

    // Returns the id of the selected PaymentShippingOption
    var shippingOption = request.shippingOption;

## Example

In the example below, the [`PaymentRequest.onshippingoptionchange`](onshippingoptionchange) and the <span class="page-not-created">`PaymentRequest.onshippingaoptionchange`</span> events are dispatched. In each calls to `updateDetails()` are made, one using a promise, and the other with a plain JS object. This demotrates synchrounous and asynchronous updates to a payment sheet.

    const request = new PaymentRequest(methodData, details, options);
    // Async update to details
    request.onshippingaddresschange = ev => {
      ev.updateWith(checkShipping(request));
    };
    // Sync update to the total
    request.onshippingoptionchange = ev => {
      const shippingOption = shippingOptions.find(
        option => option.id === request.id
      );
      const newTotal = {
        currency: "USD",
        label: "Total due",
        value: calculateNewTotal(shippingOption),
      };
      ev.updateWith({ ...details, total: newTotal });
    };
    async function checkShipping(request) {
      try {
        const json = request.shippingAddress.toJSON();

        await ensureCanShipTo(json);
        const { shippingOptions, total } = await calculateShipping(json);

        return { ...details, shippingOptions, total };
      } catch (err) {
        return { ...details, error: `Sorry! we can't ship to your address.` };
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#shippingoption-attribute">Payment Request API<br />
<span class="small">The definition of 'shippingOption' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`shippingOption`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/shippingOption" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/shippingOption</a>
