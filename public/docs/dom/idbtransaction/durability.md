# IDBTransaction.durability

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `durability` read-only property of the [`IDBTransaction`](../idbtransaction) interface returns the durability hint the transaction was created with. This is a hint to the user agent of whether to prioritize performance or durability when committing the transaction.

## Syntax

    var transactionDurability = idbTransaction.durability;

### Value

Any of the following literal [`strings`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String):

- `"strict"`: The user agent may consider that the transaction has successfully committed only after verifying that all outstanding changes have been successfully written to a persistent storage medium.
- `"relaxed"`: The user agent may consider that the transaction has successfully committed as soon as all outstanding changes have been written to the operating system, without subsequent verification.
- `"default"`: The user agent should use its default durability behavior for the storage bucket. This is the default for transactions if not otherwise specified.

## Examples

For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/) app ([view example live](https://mdn.github.io/to-do-notifications/).)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbtransaction-durability">Indexed Database API 2.0<br />
<span class="small">The definition of 'durability' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`durability`

83

83

No

No

70

No

83

83

No

59

No

13.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction/durability" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction/durability</a>
