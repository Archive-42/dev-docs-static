# Element.removeAttributeNS()

The `removeAttributeNS()` method of the [`Element`](../element) interface removes the specified attribute from an element.

## Syntax

    element.removeAttributeNS(namespace, attrName);

### Parameters

- `namespace` is a string that contains the namespace of the attribute.
- `attrName` is a string that names the attribute to be removed from the current node.

## Example

    // Given:
    //   <div id="div1" xmlns:special="http://www.mozilla.org/ns/specialspace"
    //     special:specialAlign="utterleft" width="200px" />
    d = document.getElementById("div1");
    d.removeAttributeNS("http://www.mozilla.org/ns/specialspace", "specialAlign");
    // Now: <div id="div1" width="200px" />

## Notes

DOM methods dealing with element's attributes:

<table><thead><tr class="header"><th>Not namespace-aware, most commonly used methods</th><th>Namespace-aware variants (DOM Level 2)</th><th>DOM Level 1 methods for dealing with <code>Attr</code> nodes directly (seldom used)</th><th>DOM Level 2 namespace-aware methods for dealing with <code>Attr</code> nodes directly (seldom used)</th></tr></thead><tbody><tr class="odd"><td><a href="setattribute"><code>setAttribute</code></a> (DOM 1)</td><td><a href="setattributens"><code>setAttributeNS</code></a></td><td><a href="setattributenode"><code>setAttributeNode</code></a></td><td><a href="setattributenodens"><code>setAttributeNodeNS</code></a></td></tr><tr class="even"><td><a href="getattribute"><code>getAttribute</code></a> (DOM 1)</td><td><a href="getattributens"><code>getAttributeNS</code></a></td><td><a href="getattributenode"><code>getAttributeNode</code></a></td><td><a href="getattributenodens"><code>getAttributeNodeNS</code></a></td></tr><tr class="odd"><td><a href="hasattribute"><code>hasAttribute</code></a> (DOM 2)</td><td><a href="hasattributens"><code>hasAttributeNS</code></a></td><td>-</td><td>-</td></tr><tr class="even"><td><a href="removeattribute"><code>removeAttribute</code></a> (DOM 1)</td><td><a href="removeattributens"><code>removeAttributeNS</code></a></td><td><a href="removeattributenode"><code>removeAttributeNode</code></a></td><td>-</td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-removeattributens">DOM<br />
<span class="small">The definition of 'Element: removeAttributeNS' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`removeAttributeNS`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

In Firefox 3 and later, this method resets DOM values to their defaults.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttributeNS" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttributeNS</a>
