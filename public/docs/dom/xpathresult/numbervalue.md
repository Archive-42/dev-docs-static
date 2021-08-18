XPathResult.numberValue
=======================

The read-only `numberValue` property of the [`XPathResult`](../xpathresult) interface returns the numeric value of a result with [`XPathResult.resultType`](resulttype) being `NUMBER_TYPE`.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var value = result.numberValue;

### Return value

The return value is the numeric value of the `XPathResult` returned by [`Document.evaluate()`](../document/evaluate).

### Exceptions

#### TYPE\_ERR

In case [`XPathResult.resultType`](resulttype) is not `NUMBER_TYPE`, an [`XPathException`](../xpathexception) of type `TYPE_ERR` is thrown.

Example
-------

The following example shows the use of the `numberValue` property.

### HTML

    <div>XPath example</div>
    <div>Number of &lt;div&gt;s: <output></output></div>

### JavaScript

    var xpath = "count(//div)";
    var result = document.evaluate(xpath, document, null, XPathResult.NUMBER_TYPE, null);
    document.querySelector("output").textContent = result.numberValue;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathResult-numberValue">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathResult.numberValue' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`numberValue`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/numberValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/numberValue</a>
