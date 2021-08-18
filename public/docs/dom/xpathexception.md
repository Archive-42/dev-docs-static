XPathException
==============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

In the [DOM XPath API](https://developer.mozilla.org/en-US/docs/Web/XPath) the `XPathException` interface represents exception conditions that can be encountered while performing XPath operations.

Properties
----------

 [`XPathException.code`](xpathexception/code) <span class="badge inline readonly">Read only </span>   
Returns a `short` that contains one of the [error code constants](#error_codes).

Constants
---------

<table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>INVALID_EXPRESSION_ERR</code></td><td><code>51</code></td><td>If the expression has a syntax error or otherwise is not a legal expression according to the rules of the specific <a href="xpathevaluator"><code>XPathEvaluator</code></a> or contains specialized extension functions or variables not supported by this implementation.</td></tr><tr class="even"><td><code>TYPE_ERR</code></td><td><code>52</code></td><td>If the expression cannot be converted to return the specified type.</td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathException">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathException' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XPathException`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`Document.createExpression()`](document/createexpression)
-   [`XPathExpression`](xpathexpression)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathException" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XPathException</a>
