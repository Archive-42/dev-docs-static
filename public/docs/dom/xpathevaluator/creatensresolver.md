XPathEvaluator.createNSResolver()
=================================

This method adapts any DOM node to resolve namespaces so that an XPath expression can be easily evaluated relative to the context of the node where it appeared within the document.

This adapter works like the DOM Level 3 method [`Node.lookupNamespaceURI()`](../node/lookupnamespaceuri) in resolving the namespace URI from a given prefix using the current information available in the node's hierarchy at the time the method is called, also correctly resolving the implicit `xml` prefix.

Syntax
------

    XPathNSResolver XPathEvaluator.createNSResolver(nodeResolver);

### Parameters

nodeResolver  
A [`Node`](../node) to be used as a context for namespace resolution.

### Return value

An [`XPathNSResolver`](../xpathnsresolver) object which resolves namespaces with respect to the definitions in scope for a specified node.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathEvaluator-createNSResolver">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathEvaluator.createNSResolver()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   [`Document.createNSResolver()`](../document/creatensresolver)
-   [`XPathExpression`](../xpathexpression)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathEvaluator/createNSResolver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathEvaluator/createNSResolver</a>
