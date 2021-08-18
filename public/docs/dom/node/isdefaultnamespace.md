# Node.isDefaultNamespace()

The `Node.isDefaultNamespace()` method accepts a namespace URI as an argument and returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) with a value of `true` if the namespace is the default namespace on the given node or `false` if not.

## Syntax

    result = node.isDefaultNamespace(namespaceURI);

### Parameters

`namespaceURI` is a string representing the namespace against which the element will be checked.

### Return value

`result` is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that holds the return value `true` or `false`.

## Example

    var XULNS = "http://www.mozilla.org/keymaster/gatekeeper/there.is.only.xul";
    var el = document.getElementsByTagNameNS(XULNS, 'textbox')[0];

    alert(el.isDefaultNamespace(XULNS)); // true

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-isdefaultnamespace">DOM<br />
<span class="small">The definition of 'Node: isDefaultNamespace' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`isDefaultNamespace`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/isDefaultNamespace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/isDefaultNamespace</a>
