# PaymentAddress

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PaymentAddress` interface of the [Payment Request API](payment_request_api) is used to store shipping or payment address information.

It may be useful to refer to the Universal Postal Union web site's [Addressing S42 standard](https://www.upu.int/en/Postal-Solutions/Programmes-Services/Addressing-Solutions#addressing-s42-standard) materials, which provide information about international standards for postal addresses.

## Properties

[`PaymentAddress.addressLine`](paymentaddress/addressline) <span class="badge inline readonly">Read only </span>  
An array of [`DOMString`](domstring) objects providing each line of the address not included among the other properties. The exact size and content varies by country or location and can include, for example, a street name, house number, apartment number, rural delivery route, descriptive instructions, or post office box number.

[`PaymentAddress.country`](paymentaddress/country) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) specifying the country in which the address is located, using the [ISO-3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO-3166-1_alpha-2) standard. The string is always given in its canonical upper-case form. Some examples of valid `country` values: `"US"`, `"GB"`, `"CN"`, or `"JP"`.

[`PaymentAddress.city`](paymentaddress/city) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) which contains the city or town portion of the address.

[`PaymentAddress.dependentLocality`](paymentaddress/dependentlocality) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) giving the dependent locality or sublocality within a city, for example, a neighborhood, borough, district, or UK dependent locality.

[`PaymentAddress.organization`](paymentaddress/organization) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) specifying the name of the organization, firm, company, or institution at the payment address.

[`PaymentAddress.phone`](paymentaddress/phone) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) specifying the telephone number of the recipient or contact person.

[`PaymentAddress.postalCode`](paymentaddress/postalcode) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) specifying a code used by a jurisdiction for mail routing, for example, the ZIP code in the United States or the PIN code in India.

[`PaymentAddress.recipient`](paymentaddress/recipient) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) giving the name of the recipient, purchaser, or contact person at the payment address.

[`PaymentAddress.region`](paymentaddress/region) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) containing the top level administrative subdivision of the country, for example a state, province, oblast, or prefecture.

[`PaymentAddress.regionCode`](paymentaddress/regioncode) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) specifying the region of the address, represented as a "code element" of an [ISO3166-2](https://en.wikipedia.org/wiki/ISO_3166-2) country subdivision name (e.g. "QLD" for Queensland, Australia, "CA" for California, and so on).

[`PaymentAddress.sortingCode`](paymentaddress/sortingcode) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) providing a postal sorting code such as is used in France.

**Note:** Properties for which values were not specified contain empty strings.

### Obsolete properties

The following properties are obsolete and should no longer be used, but may still be present in some browser versions.

[`PaymentAddress.languageCode`](paymentaddress/languagecode) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) indicating the language code of the address. This identifies the language in which the address is given, and is intended to aid in localization of the display of the address.

## Methods

[`PaymentAddress.toJSON()`](paymentaddress/tojson)  
A standard serializer that returns a JSON representation of the `PaymentAddress` object's properties.

## Examples

In the following example, the [`PaymentRequest()`](paymentrequest/paymentrequest) constructor is used to create a new payment request, which takes three objects as parameters — one containing details of the payment methods that can be used for the payment, one containing details of the actual order (such as items bought and shipping options), and an optional object containing further options.

The first of these three (`supportedInstruments` in the example below) contains a `data` property that has to conform to the structure defined by the [`BasicCardRequest`](basiccardrequest) dictionary.

    const supportedInstruments = [
      {
        supportedMethods: "basic-card",
      },
    ];

    const details = {
      total: { label: "Donation", amount: { currency: "USD", value: "65.00" } },
      displayItems: [
        {
          label: "Original donation amount",
          amount: { currency: "USD", value: "65.00" },
        },
      ],
      shippingOptions: [
        {
          id: "standard",
          label: "Standard shipping",
          amount: { currency: "USD", value: "0.00" },
          selected: true,
        },
      ],
    };

    const options = { requestShipping: true };

    async function doPaymentRequest() {
      const request = new PaymentRequest(supportedInstruments, details, options);
      // Add event listeners here.
      // Call show() to trigger the browser's payment flow.
      const response = await request.show();
      // Process payment.
      const json = response.toJSON();
      const httpResponse = await fetch("/pay/", { method: "POST", body: json });
      const result = httpResponse.ok ? "success" : "failure";

      await response.complete(result);
    }
    doPaymentRequest();

Once the payment flow has been triggered using [`PaymentRequest.show()`](paymentrequest/show) and the promise resolves successfully, the [`PaymentResponse`](paymentresponse) object available inside the fulfilled promise (`instrumentResponse` above) will have a [`PaymentResponse.details`](paymentresponse/details) property that will contain response details. This has to conform to the structure defined by the `BasicCardResponse` dictionary, and may look something like this:

    {
      "cardNumber' : '9999999999999999",
      "cardholderName' : 'Pat Straw",
      "cardSecurityCode" : "999",
      "expiryMonth" : "07",
      "expiryYear" : "2021",
      "billingAddress" : {
        "country" : "GB",
        // etc. billing address is a PaymentAddress object
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#paymentaddress-interface">Payment Request API<br />
<span class="small">The definition of 'PaymentAddress' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PaymentAddress`

60

15

No

Available only in nightly builds. Requires `dom.payments.request.enabled` to be set to `true` and the comma-delineated list in `dom.payments.request.supportedRegions` to contain one or more of the supported 2-character ISO locales, currently US and CA.

No

47

11.1

No

56

No

Available only in nightly builds. Requires `dom.payments.request.enabled` to be set to `true` and the comma-delineated list in `dom.payments.request.supportedRegions` to contain one or more of the supported 2-character ISO locales, currently US and CA.

44

11.3

Yes

`addressLine`

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

44

11.3

Yes

`city`

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

44

11.3

Yes

`country`

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

44

11.3

Yes

`dependentLocality`

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

44

11.3

Yes

`languageCode`

60

15

56-63

No

47

11.1-12.1

No

56

56-63

44

11.3-12.2

Yes

`organization`

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

44

11.3

Yes

`phone`

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

44

11.3

Yes

`postalCode`

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

44

11.3

Yes

`recipient`

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

44

11.3

Yes

`region`

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

44

11.3

Yes

`regionCode`

No

No

No

Available only in nightly builds.

No

No

No

No

No

No

Available only in nightly builds.

No

No

No

`sortingCode`

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

44

11.3

Yes

`toJSON`

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

44

11.3

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress</a>
