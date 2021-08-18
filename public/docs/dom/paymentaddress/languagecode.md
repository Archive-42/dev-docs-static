PaymentAddress.languageCode
===========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `languageCode` read-only property of the [`PaymentAddress`](../paymentaddress) interface returns a string containing the [BCP-47](https://datatracker.ietf.org/doc/html/bcp47) language code for the address. This is used while localizing the displayy of the address, allowing the determination of the field separators and the order of fields when formatting the address.

Syntax
------

    var paymentLanguageCode = PaymentAddress.languageCode;

### Value

A [`DOMString`](../domstring) providing the [BCP-47](https://datatracker.ietf.org/doc/html/bcp47) format language code indicating the language the address was written in, such as `"en-US"`, `"pt-BR"`, or `"ja-JP"`.

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/languageCode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/languageCode</a>
