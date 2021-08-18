XPathEvaluator.createExpression()
=================================

This method compiles an [`XPathExpression`](../xpathexpression) which can then be used for (repeated) evaluations of the [XPath](https://developer.mozilla.org/en-US/docs/Glossary/XPath) expression.

Syntax
------

    XPathExpression XPathEvaluator.createExpression(expression, resolver);

### Parameters

expression  
A [`DOMString`](../domstring) representing the XPath expression to be created.

resolver <span class="badge inline optional">Optional</span>   
Permits translation of all prefixes, including the `xml` namespace prefix, within the XPath expression into appropriate namespace URIs.

### Return value

A [`XPathExpression`](../xpathexpression) representing the compiled form of the XPath expression.

### Exceptions

#### INVALID\_EXPRESSION\_ERR

If the expression is not legal according to the rules of the `XPathEvaluator`, an [`XPathException`](../xpathexception) of type `INVALID_EXPRESSION_ERR` is raised.

#### NAMESPACE\_ERR

If the expression contains namespace prefixes which cannot be resolved by the specified [`XPathNSResolver`](../xpathnsresolver), a [`DOMException`](../domexception) of type `NAMESPACE_ERROR` is raised.

Example
-------

The following example shows the use of the `evaluate()` method.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathEvaluator-createExpression">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathEvaluator.createExpression()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   [`Document.createExpression()`](../document/createexpression)
-   [`XPathExpression`](../xpathexpression)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathEvaluator/createExpression" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathEvaluator/createExpression</a>
