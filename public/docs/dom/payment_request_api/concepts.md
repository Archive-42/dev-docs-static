# Payment processing concepts

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Draft**

This page is not complete.

The [Payment Request API](../payment_request_api) makes it easy to handle payments in a web site or app. In this article, we'll take a look at how the API operates and what each of its components does.

## Terminology

Before getting into the details of how the API operates, there are tems you'll need to know.

payee (or merchant)  
The merchant—either a person or an organization—whose web site or app wishes to receive money through the Payment Request API.

payer  
The person or organization making a purchase using a web site or app. The payer authenticates themselves, then authorizes payment, as required by the payment method.

payment method  
The instrument by which payment is submitted, such as a credit card or online payment service.

payment method provider  
An organization that provides the technology needed to submit payments using a given payment method. For example, when using a credit card to pay, the credit card processing service is the payment method provider.

payment handler  
The implementation of the code needed to interface with a particular payment method provider in order to process payments.

Some payment handlers use **merchant validation**, which is the process of validating the identity of a merchant in some way, usually using some form of cryptographic response such as a public key. Validated merchants are allowed to interface with a payment handler.

## Payment method identifiers

Payment handlers are identified by **payment method identifiers**, which are strings uniquely identifying the payment handler. These may be either one of the standardized payment handler identifiers, or a URL used by the payment processing service to both identify itself and to handle payments.

### Standardized payment method identifiers

There is currently only one registered [standardized payment method identifier](https://www.w3.org/TR/payment-method-id/#registry) (more may be added in the future):

`basic-card`  
Payments are handled by the Basic Card Payment specification. See [`BasicCardRequest`](../basiccardrequest) for details. **_Should have an article about this specification and how to use it_.**

### URL-based payment method identifiers

These may vary substantially depending on the specifics of the service, and a given processing service may have multiple URLs used, depending on the version of their API, their communication technology, and so forth.

`https://apple.com/apple-pay`  
Payments are handled using the [Apple Pay](https://www.apple.com/apple-pay/) service. Currently, Apple Pay is only supported by Safari.

`https://google.com/pay`  
Payments are processed by [Google Pay](https://pay.google.com/). This is currently supported only by Chrome and Chromium-based browsers.

## Functions of a payment handler

A [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) may provide built-in support for certain types of payments. In addition, the [Payment Handler API](https://w3c.github.io/payment-handler/) can be used to establish support for additional payment method providers, in browsers that support it. In either case, the payment handler is responsible for:

1.  **Making sure a payment can be made.** The conditions that make payment possible vary depending on the payment method and the user's payment request; for example, if the user chooses to pay using a credit card that isn't accepted by the payee, the payment can't be made.
2.  **If merchant validation is supported by the payment handler, respond to merchant validation requests from the user agent.** See [Merchant validation](#merchant_validation) for details.
3.  **Verify that the information provided by the user results in a valid transaction.** This results in the creation and returning of a payment method-specific object that contains the information needed to handle the transaction.

## Merchant validation

Some payment handlers use **merchant validation**, which is the process of validating the identity of a merchant in some way, usually using some form of cryptographic challenge. If the merchant doesn't successfully validate, it's not allowed to use the payment handler.

The exact validation technology depends on the payment handler, and merchant validation is entirely optional. In the end, the only thing that the web site or app is responsible for is fetching the merchant's validation key and passing it into the event's [`complete()`](../merchantvalidationevent/complete) method.

    paymentRequest.onmerchantvalidation = function(event) {
      event.complete(fetchValidationData(event.validationURL));
    }

In this example, `fetchValidationData()` is a function which loads the payment handler specific identifying information from the address given by `validationURL`. Note this function must go through the merchant server, because a client typically does not access the validation URL itself.

By then delivering this data (or a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to the loaded data) to the payment handler by passing it into `complete()`, the payment handler can use the retrieved data and whatever algorithm and other data to support in order to verify that the merchant can use the payment handler.

Thus, it's important to note that the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) never sends a `merchantvalidation` event, unless the user agent itself implements a payment handler. For instance, Safari has integrated support for Apple Pay, so the Apple Pay payment handler uses this to ensure that Apple Pay can be used to pay the merchant by sending `merchantvalidation` to the client, instructing it to fetch the server's validation data and deliver it to the payment handler by calling `complete()`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/">Payment Request API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/payment-method-basic-card/">Basic Card Payment</a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines <a href="../basiccardrequest"><code>BasicCardRequest</code></a> and <a href="../basiccardresponse"><code>BasicCardResponse</code></a>.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/payment-method-id/">Payment Method Identifiers</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines payment method identifiers and how they are validated, and, where applicable, minted and formally registered with the W3C.</td></tr></tbody></table>

## See also

- [Payment Request API](../payment_request_api)
- [Using the Payment Request API](using_the_payment_request_api)
- [Payment processing concepts](concepts)
- [Introducing the Payment Request API for Apple Pay](https://webkit.org/blog/8182/introducing-the-payment-request-api-for-apple-pay/)
- [Google Pay API PaymentRequest Tutorial](https://developers.google.com/pay/api/web/guides/paymentrequest/tutorial)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Payment_Request_API/Concepts" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Payment_Request_API/Concepts</a>
