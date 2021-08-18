XPathExpression
===============

This interface is a compiled XPath expression that can be evaluated on a document or specific node to return information from its [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) tree. This is useful when an expression will be reused in an application, because it is just compiled once and all namespace prefixes which occur within the expression are preresolved.

Objects of this type are created by calling [`XPathEvaluator.createExpression()`](xpathevaluator/createexpression).

Methods
-------

[`XPathExpression.evaluate()`](xpathexpression/evaluate)  
Evaluates the XPath expression on the given node or document.

Example
-------

The following example shows the use of the `XPathExpression` interface.

### HTML

    <div>XPath example</div>
    <div>Number of &lt;div&gt;s: <output></output></div>

### JavaScript

    var xpath = "//div";
    var evaluator = new XPathEvaluator();
    var expression = evaluator.createExpression(xpath);
    var result = expression.evaluate(document, XPathResult.ORDERED_NODE_SNAPSHOT_TYPE);
    document.querySelector("output").textContent = result.snapshotLength;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathExpression">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathExpression' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`XPathExpression`

1

12

Yes

No

≤12.1

3

1

18

Yes

≤12.1

1

1.0

`evaluate`

1

12

Yes

No

≤12.1

3

1

18

Yes

≤12.1

1

1.0

See also
--------

-   [`document.createExpression()`](document/createexpression)
-   [`XPathResult`](xpathresult)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathExpression" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathExpression</a>
