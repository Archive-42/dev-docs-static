# Node.lookupNamespaceURI()

The `Node.lookupNamespaceURI()` method accepts a prefix and returns the namespace URI associated with it on the given node if found (and `null` if not).

## Syntax

    var namespace = node.lookupNamespaceURI(prefix);

### Parameters

`prefix`  
The prefix to look for. If this parameter is `null`, the method will return the default namespace URI, if any.

### Return value

A [`DOMString`](../domstring) containing the namespace URI. If the prefix is not found, it returns `null`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-lookupnamespaceuri">DOM<br />
<span class="small">The definition of 'Node: lookupNamespaceURI' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`lookupNamespaceURI`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/lookupNamespaceURI" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/lookupNamespaceURI</a>
