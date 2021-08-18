XPathResult.snapshotLength
==========================

The read-only `snapshotLength` property of the [`XPathResult`](../xpathresult) interface represents the number of nodes in the result snapshot.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var snapshotLength = result.snapshotLength;

### Return value

An integer value representing the number of nodes in the result snapshot.

### Exceptions

#### TYPE\_ERR

In case [`XPathResult.resultType`](resulttype) is not `UNORDERED_NODE_SNAPSHOT_TYPE` or `ORDERED_NODE_SNAPSHOT_TYPE`, an [`XPathException`](../xpathexception) of type `TYPE_ERR` is thrown.

Example
-------

The following example shows the use of the `snapshotLength` property.

### HTML

    <div>XPath example</div>
    <div>Number of matched nodes: <output></output></div>

### JavaScript

    var xpath = "//div";
    var result = document.evaluate(xpath, document, null, XPathResult.ORDERED_NODE_SNAPSHOT_TYPE, null);
    document.querySelector("output").textContent = result.snapshotLength;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathResult-snapshotLength">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathResult.snapshotLength' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`snapshotLength`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/snapshotLength" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/snapshotLength</a>
