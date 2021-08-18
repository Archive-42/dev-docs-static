XPathEvaluator
==============

The `XPathEvaluator` interface allows to compile and evaluate [XPath](https://developer.mozilla.org/en-US/docs/Glossary/XPath) expressions.

It is implemented by the [`Document`](document) interface.

Methods
-------

[`XPathEvaluator.createExpression()`](xpathevaluator/createexpression)  
Creates a parsed XPath expression with resolved namespaces.

[`XPathEvaluator.createNSResolver()`](xpathevaluator/creatensresolver)  
Adapts any DOM node to resolve namespaces allowing the XPath expression to be evaluated relative to the context of the node where it appeared within the document.

[`XPathEvaluator.evaluate()`](xpathevaluator/evaluate)  
Evaluates an XPath expression string and returns a result of the specified type if possible.

Example
-------

The following example shows the use of the `XPathEvaluator` interface.

### HTML

    <div>XPath example</div>
    <div>Number of &lt;div&gt;s: <output></output></div>

### JavaScript

    var xpath = "//div";
    var evaluator = new XPathEvaluator();
    var expression = evaluator.createExpression("//div");
    var result = expression.evaluate(document, XPathResult.ORDERED_NODE_SNAPSHOT_TYPE);
    document.querySelector("output").textContent = result.snapshotLength;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathEvaluator">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathEvaluator' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`XPathEvaluator`

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

`XPathEvaluator`

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

`createExpression`

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

`createNSResolver`

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

`evaluate`

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

See also
--------

-   [`document.createExpression()`](document/createexpression)
-   [`XPathExpression`](xpathexpression)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathEvaluator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathEvaluator</a>
