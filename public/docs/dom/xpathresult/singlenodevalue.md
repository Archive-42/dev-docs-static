XPathResult.singleNodeValue
===========================

The read-only `singleNodeValue` property of the [`XPathResult`](../xpathresult) interface returns a [`Node`](../node) value or `null` in case no node was matched of a result with [`XPathResult.resultType`](resulttype) being `ANY_UNORDERED_NODE_TYPE` or `FIRST_ORDERED_NODE_TYPE`.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var value = result.singleNodeValue;

### Return value

The return value is the [`Node`](../node) value of the `XPathResult` returned by [`Document.evaluate()`](../document/evaluate).

### Exceptions

#### TYPE\_ERR

In case [`XPathResult.resultType`](resulttype) is not `ANY_UNORDERED_NODE_TYPE` or `FIRST_ORDERED_NODE_TYPE`, an [`XPathException`](../xpathexception) of type `TYPE_ERR` is thrown.

Example
-------

The following example shows the use of the `singleNodeValue` property.

### HTML

    <div>XPath example</div>
    <div>Tag name of the element having the text content 'XPath example': <output></output></div>

### JavaScript

    var xpath = "//*[text()='XPath example']";
    var result = document.evaluate(xpath, document, null, XPathResult.FIRST_ORDERED_NODE_TYPE, null);
    document.querySelector("output").textContent = result.singleNodeValue.localName;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathResult-singleNodeValue">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathResult.singleNodeValue' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`singleNodeValue`

1

12

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/singleNodeValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/singleNodeValue</a>
