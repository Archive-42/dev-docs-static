XPathResult.snapshotItem()
==========================

The `snapshotItem()` method of the [`XPathResult`](../xpathresult) interface returns an item of the snapshot collection or `null` in case the index is not within the range of nodes. Unlike the iterator result, the snapshot does not become invalid, but may not correspond to the current document if it is mutated.

Syntax
------

    var node = result.snapshotItem(i);

### Return value

The [`Node`](../node) at the given index within the node set of the `XPathResult`.

### Exceptions

#### TYPE\_ERR

In case [`XPathResult.resultType`](resulttype) is not `UNORDERED_NODE_SNAPSHOT_TYPE` or `ORDERED_NODE_SNAPSHOT_TYPE`, an [`XPathException`](../xpathexception) of type `TYPE_ERR` is thrown.

Example
-------

The following example shows the use of the `snapshotItem()` method.

### HTML

    <div>XPath example</div>
    <div>Tag names of the matched nodes: <output></output></div>

### JavaScript

    var xpath = "//div";
    var result = document.evaluate(xpath, document, null, XPathResult.ORDERED_NODE_SNAPSHOT_TYPE, null);
    var node = null;
    var tagNames = [];
    for(var i = 0; i < result.snapshotLength; i++) {
      var node = result.snapshotItem(i);
      tagNames.push(node.localName);
    }
    document.querySelector("output").textContent = tagNames.join(", ");

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathResult-snapshotItem">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathResult.snapshotItem()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XPathResult.snapshotItem()`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/snapshotItem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/snapshotItem</a>
