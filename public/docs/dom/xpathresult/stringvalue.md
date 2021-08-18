XPathResult.stringValue
=======================

The read-only `stringValue` property of the [`XPathResult`](../xpathresult) interface returns the string value of a result with [`XPathResult.resultType`](resulttype) being `STRING_TYPE`.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var value = result.stringValue;

### Return value

The return value is the string value of the `XPathResult` returned by [`Document.evaluate()`](../document/evaluate).

### Exceptions

#### TYPE\_ERR

In case [`XPathResult.resultType`](resulttype) is not `STRING_TYPE`, an [`XPathException`](../xpathexception) of type `TYPE_ERR` is thrown.

Example
-------

The following example shows the use of the `stringValue` property.

### HTML

    <div>XPath example</div>
    <div>Text content of the &lt;div&gt; above: <output></output></div>

### JavaScript

    var xpath = "//div/text()";
    var result = document.evaluate(xpath, document, null, XPathResult.STRING_TYPE, null);
    document.querySelector("output").textContent = result.stringValue;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathResult-stringValue">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathResult.stringValue' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`stringValue`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/stringValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/stringValue</a>
