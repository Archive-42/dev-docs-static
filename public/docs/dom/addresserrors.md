# AddressErrors

The `AddressErrors` dictionary is used by the [Payment Request API](payment_request_api) to report validation errors in a physical address (typically a billing address or a shipping address). Any members which is present indicates that a validation error occurred for the member of the same name in an address described using [`PaymentAddress`](paymentaddress).

`AddressErrors` is the type of the object returned by [`shippingAddressErrors`](paymentdetailsupdate/shippingaddresserrors) in the [`PaymentDetailsUpdate`](paymentdetailsupdate) passed into [`PaymentRequestUpdateEvent.updateWith()`](paymentrequestupdateevent/updatewith) by the `shippingaddresschange` event handler if a change to the address resulted in a validation error occurring.

See the [examples below](#examples) to see how this works.

## Properties

[`addressLine`](addresserrors/addressline)  
A [`DOMString`](domstring) which, if present, indicates that the [`addressLine`](paymentaddress/addressline) property of the [`PaymentAddress`](paymentaddress) could not be validated. The contents of the string provide a human-readable explanation of the validation failure, and ideally suggestions to correct the problem.

[`city`](addresserrors/city)  
A [`DOMString`](domstring) which, if present, indicates that the [`city`](paymentaddress/city) property of the [`PaymentAddress`](paymentaddress) could not be validated. The contents of the string provide a human-readable explanation of the validation failure, and ideally suggestions to correct the problem.

[`country`](addresserrors/country)  
A [`DOMString`](domstring) which, if present, indicates that the [`country`](paymentaddress/country) property of the [`PaymentAddress`](paymentaddress) could not be validated. The contents of the string provide a human-readable explanation of the validation failure, and ideally suggestions to correct the problem.

[`dependentLocality`](addresserrors/dependentlocality)  
A [`DOMString`](domstring) which, if present, indicates that the [`dependentLocality`](paymentaddress/dependentlocality) property of the [`PaymentAddress`](paymentaddress) could not be validated. The contents of the string provide a human-readable explanation of the validation failure, and ideally suggestions to correct the problem.

[`organization`](addresserrors/organization)  
A [`DOMString`](domstring) which, if present, indicates that the [`organization`](paymentaddress/organization) property of the [`PaymentAddress`](paymentaddress) could not be validated. The contents of the string provide a human-readable explanation of the validation failure, and ideally suggestions to correct the problem.

[`phone`](addresserrors/phone)  
A [`DOMString`](domstring) which, if present, indicates that the [`phone`](paymentaddress/phone) property of the [`PaymentAddress`](paymentaddress) could not be validated. The contents of the string provide a human-readable explanation of the validation failure, and ideally suggestions to correct the problem.

[`postalCode`](addresserrors/postalcode)  
A [`DOMString`](domstring) which, if present, indicates that the [`postalCode`](paymentaddress/postalcode) property of the [`PaymentAddress`](paymentaddress) could not be validated. The contents of the string provide a human-readable explanation of the validation failure, and ideally suggestions to correct the problem.

[`recipient`](addresserrors/recipient)  
A [`DOMString`](domstring) which, if present, indicates that the [`recipient`](paymentaddress/recipient) property of the [`PaymentAddress`](paymentaddress) could not be validated. The contents of the string provide a human-readable explanation of the validation failure, and ideally suggestions to correct the problem.

[`region`](addresserrors/region)  
A [`DOMString`](domstring) which, if present, indicates that the [`region`](paymentaddress/region) property of the [`PaymentAddress`](paymentaddress) could not be validated. The contents of the string provide a human-readable explanation of the validation failure, and ideally suggestions to correct the problem.

[`regionCode`](addresserrors/regioncode)  
A [`DOMString`](domstring) which, if present, indicates that the [`regionCode`](paymentaddress/regioncode) property of the [`PaymentAddress`](paymentaddress) could not be validated. The contents of the string provide a human-readable explanation of the validation failure, and ideally suggestions to correct the problem.

[`sortingCode`](addresserrors/sortingcode)  
A [`DOMString`](domstring) which, if present, indicates that the [`sortingCode`](paymentaddress/sortingcode) property of the [`PaymentAddress`](paymentaddress) could not be validated. The contents of the string provide a human-readable explanation of the validation failure, and ideally suggestions to correct the problem.

### Obsolete properties

These properties have been removed from the specification and should no longer be used.

[`languageCode`](addresserrors/languagecode) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) which, if present, indicates that the [`languageCode`](paymentaddress/languagecode) property of the [`PaymentAddress`](paymentaddress) could not be validated. The contents of the string provide a human-readable explanation of the validation failure, and ideally suggestions to correct the problem.

## Usage notes

Keep in mind that some violation errors may be outside the ability of the user to fix. Try to avoid asking the user to make corrections to things they can't change, and there may be situations in which you need to allow validation errors to be accepted anyway (for example, if you validate addresses against a postal service database and a new home has been built and its address is not yet in the database).

## Examples

### Snippet: Limiting destination countries

This first example is just a snippet showing an implementation of the event handler for the `shippingaddresschange` event which checks to be sure the chosen address is located within one of a limited number of countries.

    function handleAddressChange(ev) {
      const validCountries = ["US", "CA", "GB", "JP", "CN", "MX"];

      const genericAddressError = "Unable to ship to the given address. Please check for any errors.";
      const invalidCountryError = "At this time, we only ship to the United States, Canada, Great Britain, Japan, China, and Germany.";

      let shippingAddress = ev.target.shippingAddress;
      let shippingAddressErrors = {};
      let updateDetails = {};

      if (!validCountries.includes(shippingAddress.country)) {
        ev.target.shippingOptions = [];
        shippingAddressErrors.country = invalidCountryError;

        updateDetails = {
          error: genericAddressError,
          shippingAddressErrors,
          ...defaultPaymentDetails
        };
      }

      ev.updateWith(updateDetails);
    }

See [Handling address changes](#handling_address_changes) for a description of how this code works.

### Complete example

Here we'll see a complete, working version of the example above (except of course that it's not connected to an actual payment handler, so no payments are actually processed). In the example, we're handling a donation to an organization that will be sending a "thank you" gift to the donor, so it requests shipping information along with allowing the donation payment itself.

#### JavaScript

##### Payment Request data

First, we declare the variables `supportedHandlers`, which is compatible with <span class="page-not-created">`PaymentMethodData`</span>, and `defaultPaymentDetails`, which is a [`PaymentDetailsUpdate`](paymentdetailsupdate) object.

    let supportedHandlers = [
      {
        supportedMethods: "basic-card",
        data: {
          supportedNetworks: ["visa", "mastercard", "amex", "discover"],
          supportedTypes: ["credit", "debit"]
        }
      }
    ];

    let defaultPaymentDetails = {
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

`supportedHandlers` describes the supported payment handlers and the details for those. In this example, only the Basic Card handler is supported, and it's configured to permit both debit and credit cards from Visa, Master Card, American Express, and Discover.

`defaultPaymentDetails` describes the payment being requested. A description of the total amount being requested (including a label and the currency used), a list of the line items (in this case only one, "Original donation amount"), and a list of shipping options available; in this case only one.

##### Process the payment

The main payment processing code is found in the `process()` method, up next.

    let request;

    function process() {
      let options = {requestShipping: true};

      try {
        request = new PaymentRequest(supportedHandlers, defaultPaymentDetails, options);
        // Add event listeners here.
        request.onshippingaddresschange = handleAddressChange;
        // Call show() to trigger the browser's payment flow.
        request.show().then(function(instrumentResponse) {
          // Do something with the response from the UI.
          console.log("Got response!");
        })
        .catch(function(err) {
          // Do something with the error from request.show().
          console.error(`Error from show(): ${err}`);
        });
      } catch (e) {
        // Catch any errors from trying to create the PaymentRequest object.
      }
    }

This code creates a new [`PaymentRequest`](paymentrequest), providing the supported handlers and payment options we set up above, as well as additional options (in this case, that we want to ask for shipping information).

After that, we set up the handler for the `shippingaddresschange` event so we can validate address information and call the request's [`show()`](paymentrequest/show) method to start running the payment UI.

##### Handling address changes

The `handleAddressChange()` method, called when `shippingaddresschange` events occur, is where we'll look to see if the country is one of those we allow as shipping destinations.

    function handleAddressChange(ev) {
      const validCountries = ["US", "CA", "GB", "JP", "CN", "MX"];

      const genericAddressError = "Unable to ship to the given address. Please check for any errors.";
      const invalidCountryError = "At this time, we only ship to the United States, Canada, Great Britain, Japan, China, and Germany.";

      let shippingAddress = ev.target.shippingAddress;
      let shippingAddressErrors = {};
      let updateDetails = {};

      if (!validCountries.includes(shippingAddress.country)) {
        ev.target.shippingOptions = [];
        shippingAddressErrors.country = invalidCountryError;

        updateDetails = {
          error: genericAddressError,
          shippingAddressErrors,
          ...defaultPaymentDetails
        };
      }

      ev.updateWith(updateDetails);
    }

The `shippingaddresschange` event doesn't receive the [`PaymentRequest`](paymentrequest) object directly, so we fetch it from the [`target`](event/target) property of the event. If the request's [`shippingAddress`](paymentrequest/shippingaddress) has a value for [`country`](paymentaddress/country) which isn't in the array `validCountries`, we generate the error.

That's done by removing all shipping options currently set on the request, then set up an object named `shippingAddressErrors` which contains a `country` property which is an error message describing why the stated country isn't being permitted as a value.

Then a [`PaymentDetailsUpdate`](paymentdetailsupdate) object is created with its [`error`](paymentdetailsupdate/error) set to a generic message about address errors and with the reset of the object's values taken from `shippingAddressErrors`, and, using "`...defaultPaymentDetails`" as the final entry in the object, the remeainder of the properties' values are taken from `defaultPaymentDetails`.

The final step is to call the event's [`updateWith()`](paymentrequestupdateevent/updatewith) method, passing along the `updateDetails` object. This lets the Payment Request API know to present the specified error or errors but to allow the user to keep trying to edit the address.

##### Setting up the Donate Now button

This code creates a handler for the `load` event on the [`window`](window) which in turn adds the needed `click` event handler to the "Donate Now" button so that clicking it starts the payment process.

    window.addEventListener("load", function(ev) {
      document.getElementById("pay").addEventListener("click", process, false);
    }, false);

See [`addEventListener()`](eventtarget/addeventlistener) for information about event handlers and how they work.

#### HTML

Here's the simple HTML for this example.

    <p>Donate US $65 to our worthwhile cause and we will send you a totally
    not-useless gift as a token of our thanks!</p>
    <button id="pay">Donate Now</button>

#### Result

The final product is below.

**Note:** if you have content blocking features enabled in your browser, the example may not work inline below. In that case, you can [view the example on its own page](https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Web/API/AddressErrors/_samples_/Complete_example).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-addresserrors">Payment Request API<br />
<span class="small">The definition of 'AddressErrors' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.AddressErrors`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors</a>
