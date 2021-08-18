XPathNSResolver
===============

The `XPathNSResolver` interface permits prefix strings in an [XPath](https://developer.mozilla.org/en-US/docs/Glossary/XPath) expression to be properly bound to namespace URI strings.

The [`XPathEvaluator`](xpathevaluator) interface can construct an implementation of `XPathNSResolver` from a node, or the interface may be implemented by any application.

Methods
-------

[`XPathNSResolver.lookupNamespaceURI()`](xpathnsresolver/lookupnamespaceuri)  
Looks up the namespace URI associated to the given namespace prefix.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathNSResolver">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathNSResolver' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XPathNSResolver`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`XPathEvaluator`](xpathevaluator)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathNSResolver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathNSResolver</a>
