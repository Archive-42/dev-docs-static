# Document.createNSResolver()

Creates an `XPathNSResolver` which resolves namespaces with respect to the definitions in scope for a specified node.

## Syntax

    nsResolver = document.createNSResolver(node);

### Parameters

- `node` is the node to be used as a context for namespace resolution.

### Return value

- `nsResolver` is an XPathNSResolver object.

## Notes

Adapts any DOM node to resolve namespaces so that an [XPath](https://developer.mozilla.org/en-US/docs/Web/XPath) expression can be easily evaluated relative to the context of the node where it appeared within the document. This adapter works like the DOM Level 3 method `lookupNamespaceURI` on nodes in resolving the `namespaceURI` from a given prefix using the current information available in the node's hierarchy at the time `lookupNamespaceURI` is called. Also correctly resolves the implicit `xml` prefix.

Note, XPath defines QNames without prefix to match only elements in the null namespace. There is no way in XPath to pick up the default namespace as applied to a regular element reference (e.g., `p[@id='_myid'`\] for `xmlns='http://www.w3.org/1999/xhtml'`). To match default elements in a non-null namespace, you either have to refer to a particular element using a form such as `*namespace-uri()=http://www.w3.org/1999/xhtml and name()=p[@id='_myid']` ([this approach](https://developer.mozilla.org/en-US/docs/Web/XPath/Introduction_to_using_XPath_in_JavaScript#using_xpath_functions_to_reference_elements_with_its_default_namespace) works well for dynamic XPath expressions where the namespaces might not be known) or use prefixed name tests, and create a namespace resolver mapping the prefix to the namespace. Read more on [how to create a user defined namespace resolver](https://developer.mozilla.org/en-US/docs/Web/XPath/Introduction_to_using_XPath_in_JavaScript#implementing_a_user_defined_namespace_resolver) if you wish to take the latter approach.

`createNSResolver` was introduced in DOM Level 3.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathEvaluator-createNSResolver">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'document.createNSResolver' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

## See also

- [document.evaluate](evaluate)
- [Introduction to using XPath in JavaScript](https://developer.mozilla.org/en-US/docs/Web/XPath/Introduction_to_using_XPath_in_JavaScript)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createNSResolver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createNSResolver</a>
