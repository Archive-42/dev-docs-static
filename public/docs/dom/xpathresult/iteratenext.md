XPathResult.iterateNext()
=========================

The `iterateNext()` method of the [`XPathResult`](../xpathresult) interface iterates over a node set result and returns the next node from it or `null` if there are no more nodes.

Syntax
------

    var node = result.iterateNext();

### Return value

The next [`Node`](../node) within the node set of the `XPathResult`.

### Exceptions

#### TYPE\_ERR

In case [`XPathResult.resultType`](resulttype) is not `UNORDERED_NODE_ITERATOR_TYPE` or `ORDERED_NODE_ITERATOR_TYPE`, an [`XPathException`](../xpathexception) of type `TYPE_ERR` is thrown.

#### INVALID\_STATE\_ERR

If the document is mutated since the result was returned, an [`XPathException`](../xpathexception) of type `INVALID_STATE_ERR` is thrown.

Example
-------

The following example shows the use of the `iterateNext()` method.

### HTML

    <div>XPath example</div>
    <div>Tag names of the matched nodes: <output></output></div>

### JavaScript

    var xpath = "//div";
    var result = document.evaluate(xpath, document, null, XPathResult.ANY_TYPE, null);
    var node = null;
    var tagNames = [];
    while(node = result.iterateNext()) {
      tagNames.push(node.localName);
    }
    document.querySelector("output").textContent = tagNames.join(", ");

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathResult-iterateNext">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathResult.iterateNext()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XPathResult.iterateNext()`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/iterateNext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/iterateNext</a>
