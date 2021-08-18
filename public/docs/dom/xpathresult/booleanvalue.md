XPathResult.booleanValue
========================

The read-only `booleanValue` property of the [`XPathResult`](../xpathresult) interface returns the boolean value of a result with [`XPathResult.resultType`](resulttype) being `BOOLEAN_TYPE`.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var value = result.booleanValue;

### Return value

The return value is the boolean value of the `XPathResult` returned by [`Document.evaluate()`](../document/evaluate).

### Exceptions

#### TYPE\_ERR

In case [`XPathResult.resultType`](resulttype) is not `BOOLEAN_TYPE`, an [`XPathException`](../xpathexception) of type `TYPE_ERR` is thrown.

Example
-------

The following example shows the use of the `booleanValue` property.

### HTML

    <div>XPath example</div>
    <p>Text is 'XPath example': <output></output></p>

### JavaScript

    var xpath = "//div/text() = 'XPath example'";
    var result = document.evaluate(xpath, document, null, XPathResult.BOOLEAN_TYPE, null);
    document.querySelector("output").textContent = result.booleanValue;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathResult-booleanValue">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathResult.booleanValue' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`booleanValue`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/booleanValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/booleanValue</a>
