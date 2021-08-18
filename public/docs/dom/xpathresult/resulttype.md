XPathResult.resultType
======================

The read-only `resultType` property of the [`XPathResult`](../xpathresult) interface represents the type of the result, as defined by the type constants.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var resultType = result.resultType;

### Return value

An integer value representing the type of the result, as defined by the [type constants](#).

Constants
---------

<table><thead><tr class="header"><th>Result Type Defined Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>ANY_TYPE</code></td><td><code>0</code></td><td>A result set containing whatever type naturally results from evaluation of the expression. Note that if the result is a node-set then <code>UNORDERED_NODE_ITERATOR_TYPE</code> is always the resulting type.</td></tr><tr class="even"><td><code>NUMBER_TYPE</code></td><td><code>1</code></td><td>A result containing a single number. This is useful for example, in an XPath expression using the <code>count()</code> function.</td></tr><tr class="odd"><td><code>STRING_TYPE</code></td><td><code>2</code></td><td>A result containing a single string.</td></tr><tr class="even"><td><code>BOOLEAN_TYPE</code></td><td><code>3</code></td><td>A result containing a single boolean value. This is useful for example, in an XPath expression using the <code>not()</code> function.</td></tr><tr class="odd"><td><code>UNORDERED_NODE_ITERATOR_TYPE</code></td><td><code>4</code></td><td>A result node-set containing all the nodes matching the expression. The nodes may not necessarily be in the same order that they appear in the document.</td></tr><tr class="even"><td><code>ORDERED_NODE_ITERATOR_TYPE</code></td><td><code>5</code></td><td>A result node-set containing all the nodes matching the expression. The nodes in the result set are in the same order that they appear in the document.</td></tr><tr class="odd"><td><code>UNORDERED_NODE_SNAPSHOT_TYPE</code></td><td><code>6</code></td><td>A result node-set containing snapshots of all the nodes matching the expression. The nodes may not necessarily be in the same order that they appear in the document.</td></tr><tr class="even"><td><code>ORDERED_NODE_SNAPSHOT_TYPE</code></td><td><code>7</code></td><td>A result node-set containing snapshots of all the nodes matching the expression. The nodes in the result set are in the same order that they appear in the document.</td></tr><tr class="odd"><td><code>ANY_UNORDERED_NODE_TYPE</code></td><td><code>8</code></td><td>A result node-set containing any single node that matches the expression. The node is not necessarily the first node in the document that matches the expression.</td></tr><tr class="even"><td><code>FIRST_ORDERED_NODE_TYPE</code></td><td><code>9</code></td><td>A result node-set containing the first node in the document that matches the expression.</td></tr></tbody></table>

Example
-------

The following example shows the use of the `resultType` property.

### HTML

    <div>XPath example</div>
    <div>Is XPath result a node set: <output></output></div>

### JavaScript

    var xpath = "//div";
    var result = document.evaluate(xpath, document, null, XPathResult.ANY_TYPE, null);
    document.querySelector("output").textContent =
      result.resultType >= XPathResult.UNORDERED_NODE_ITERATOR_TYPE &&
      result.resultType <= XPathResult.FIRST_ORDERED_NODE_TYPE;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathResult-resultType">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathResult.resultType' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`resultType`

Yes

12

Yes

No

Yes

3

Yes

Yes

Yes

Yes

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/resultType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathResult/resultType</a>
