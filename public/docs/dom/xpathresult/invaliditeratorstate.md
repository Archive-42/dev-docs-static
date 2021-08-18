XPathResult.invalidIteratorState
================================

The read-only `invalidIteratorState` property of the [`XPathResult`](../xpathresult) interface signifies that the iterator has become invalid. It is `true` if [`XPathResult.resultType`](resulttype) is `UNORDERED_NODE_ITERATOR_TYPE` or `ORDERED_NODE_ITERATOR_TYPE` and the document has been modified since this result was returned.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var iteratorState = result.invalidIteratorState;

### Return value

A boolean value indicating whether the iterator has become invalid.

Example
-------

The following example shows the use of the `invalidIteratorState` property.

### HTML

    <div>XPath example</div>
    <p>Iterator state: <output></output></p>

### JavaScript

    var xpath = "//div";
    var result = document.evaluate(xpath, document, null, XPathResult.ANY_TYPE, null);
    // Invalidates the iterator state
    document.querySelector("div").remove();
    document.querySelector("output").textContent = result.invalidIteratorState ? "invalid" : "valid";

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathResult-invalid-iterator-state">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathResult.invalidIteratorState' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`invalidIteratorState`

Yes

12

Yes

No

Yes

3

Yes

Yes

Yes

Yes

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/invalidIteratorState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/invalidIteratorState</a>
