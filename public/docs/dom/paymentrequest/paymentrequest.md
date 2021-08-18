# PaymentRequest.PaymentRequest()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PaymentRequest()` constructor creates a new [`PaymentRequest`](../paymentrequest) object which will be used to handle the process of generating, validating, and submitting a payment request.

## Syntax

    var paymentRequest = new PaymentRequest(methodData, details, [options]);

### Parameters

`methodData`  
Contains an array of identifiers for the payment methods the merchant web site accepts and any associated payment method specific data. Each item in the array contains the following fields:

`supportedMethods`  
For early implementations of the spec, this was a sequence of identifiers for payment methods that the merchant website accepts. Starting with more recent browsers, this parameter is more generic than credit cards, it is a single [`DOMString`](../domstring), and the meaning of the `data` parameter changes with the `supportedMethods`. For example, the basic card payment method is selected by specifying the string `basic-card` here.

`data`  
A JSON-serializable object that provides optional information that might be needed by the supported payment methods. This has to conform to the type expected by the payment handler indicated by `supportedMethods`. For basic credit card services, this structure should match the [`BasicCardRequest`](../basiccardrequest) dictionary.

`details`  
Provides information about the requested transaction. This parameter contains the following fields:

`total`  
The total amount of the payment request.

`id` <span class="badge inline optional">Optional</span>  
A free-form identifier for this payment request. If a value is not supplied, the browser will construct one.

`displayItems`  
An array of optional line items for the payment request that the user agent may display, such as product details, tax, and shipping.

`shippingOptions`  
The shipping options the user may choose from. If this sequence is blank, it indicates the merchant cannot ship to the current shipping address. The default shipping option may be indicated in this sequence.

`modifiers`  
Modifiers for specific payment methods; for example, adjusting the total amount based on the payment method. This parameter contains the following fields:

`additionalDisplayItems`  
An array of items to be appended to the `details.displayItems` property. This property is commonly used to add a discount or surcharge line item indicating the different amount in `details.modifiers.total`.

`data`  
A JSON-serializable object that provides optional information that might be needed by the supported payment methods. This has to conform to the structure defined in the [`BasicCardRequest`](../basiccardrequest) dictionary.

`total`  
A total amount for the payment request that overrides value in details.total. This is typically used when `details.modifiers.additionalItems` adds a discount or a surchase to the request.

`options` <span class="badge inline optional">Optional</span>  
Lets you set options that control the behavior of the user agent. This parameter contains the following fields:

`requestPayerName`  
A Boolean indicating whether the user agent should collect the payer's name and submit it with the payment request. The default is `false`.

`requestPayerEmail`  
A Boolean indicating whether the user agent should collect the payer's email address and submit it with the payment request. The default is `false`.

`requestPayerPhone`  
A Boolean indicating whether the user agent should collect the payer's phone number and submit it with the payment request. The default is `false`.

`requestShipping`  
A Boolean indicating whether the user agent should collect the payer's shipping address and submit it with the payment request. If you set this type to true, you should select an appropriate `shippingType`. The default is `false`.

`shippingType`  
Lets you specify how the user interface refers to shipping when the word 'shipping' isn't appropriate for your use case. For example, in English speaking countries you would say "pizza delivery" not "pizza shipping". Valid values are `"shipping"`, `"delivery"`, and `"pickup"`. Quotation marks must be included. The default value is `"shipping"`.

### Return value

A new [`PaymentRequest`](../paymentrequest) object, configured for use as configured by the input parameters.

## Examples

The following example shows minimal functionality and focuses instead on showing the complete context of instantiating a `PaymentRequest` object.

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#constructor">Payment Request API<br />
<span class="small">The definition of 'PaymentRequest() constructor' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PaymentRequest`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/PaymentRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/PaymentRequest</a>
