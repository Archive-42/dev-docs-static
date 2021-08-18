XPathNSResolver.lookupNamespaceURI()
====================================

The `lookupNamespaceURI` method looks up the namespace URI associated to the given namespace prefix within an [XPath](https://developer.mozilla.org/en-US/docs/Glossary/XPath) expression evaluated by the [`XPathEvaluator`](../xpathevaluator) interface.

Syntax
------

    DOMString XPathNSResolver.lookupNamespaceURI(prefix);

### Parameters

prefix  
A [`DOMString`](../domstring) representing the prefix to look for.

### Return value

A [`DOMString`](../domstring) representing the associated namespace URI or `null` if none is found.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathNSResolver-lookupNamespaceURI">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathNSResolver.lookupNamespaceURI()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XPathNSResolver.lookupNamespaceURI`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`XPathEvaluator`](../xpathevaluator)
-   [`Node.lookupNamespaceURI()`](../node/lookupnamespaceuri)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathNSResolver/lookupNamespaceURI" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathNSResolver/lookupNamespaceURI</a>
