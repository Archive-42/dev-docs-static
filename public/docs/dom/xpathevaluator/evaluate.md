XPathEvaluator.evaluate()
=========================

The `evaluate()` method of the [`XPathEvaluator`](../xpathevaluator) interface executes an XPath expression on the given node or document and returns an [`XPathResult`](../xpathresult).

Syntax
------

    XPathResult XPathEvaluator.evaluate(expression, contextNode, resolver, type, result);

### Parameters

expression  
A [`DOMString`](../domstring) representing the XPath expression to be parsed and evaluated.

contextNode  
A [`Node`](../node) representing the context to use for evaluating the expression.

resolver <span class="badge inline optional">Optional</span>   
Permits translation of all prefixes, including the `xml` namespace prefix, within the XPath expression into appropriate namespace URIs.

type <span class="badge inline optional">Optional</span>   
Specifies the type of result to be returned by evaluating the expression. This must be one of the [`XPathResult.Constants`](../xpathresult#constants).

result <span class="badge inline optional">Optional</span>   
Allows to specify a result object which may be reused and returned by this method. If this is specified as `null` or the implementation does not reuse the specified result, a new result object will be returned.

### Return value

An [`XPathResult`](../xpathresult) object representing the result of evaluating the XPath expression.

### Exceptions

#### INVALID\_EXPRESSION\_ERR

If the expression is not legal according to the rules of the [`XPathEvaluator`](../xpathevaluator), an [`XPathException`](../xpathexception) of type `INVALID_EXPRESSION_ERR` is raised.

#### TYPE\_ERR

In case result cannot be converted to the specified type, an [`XPathException`](../xpathexception) of type `TYPE_ERR` is raised.

#### NAMESPACE\_ERR

If the expression contains namespace prefixes which cannot be resolved by the specified [`XPathNSResolver`](../xpathnsresolver), a [`DOMException`](../domexception) of type `NAMESPACE_ERROR` is raised.

#### WRONG\_DOCUMENT\_ERR

If the provided context node is from a document that is not supported by the [`XPathEvaluator`](../xpathevaluator), a [`DOMException`](../domexception) of type `WRONG_DOCUMENT_ERR` is raised.

#### NOT\_SUPPORTED\_ERR

If the provided context node is not a type permitted as an XPath context node or the request type is not permitted by the [`XPathEvaluator`](../xpathevaluator), a [`DOMException`](../domexception) of type `NOT_SUPPORTED_ERR` is raised.

Example
-------

The following example shows the use of the `evaluate()` method.

### HTML

    <div>XPath example</div>
    <div>Number of &lt;div&gt;s: <output></output></div>

### JavaScript

    var evaluator = new XPathEvaluator();
    var result = evaluator.evaluate("//div", document, null, XPathResult.ORDERED_NODE_SNAPSHOT_TYPE);
    document.querySelector("output").textContent = result.snapshotLength;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathEvaluator-evaluate">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathEvaluator.evaluate()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XPathEvaluator.evaluate()`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathEvaluator/evaluate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathEvaluator/evaluate</a>
