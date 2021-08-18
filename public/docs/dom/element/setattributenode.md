# Element.setAttributeNode()

The `setAttributeNode()` method adds a new `Attr` node to the specified element.

## Syntax

    var replacedAttr = element.setAttributeNode(attribute);

- `attribute` is the `Attr` node to set on the element.
- `replacedAttr` is the replaced attribute node, if any, returned by this function.

## Example

This example copies the `align` attribute from one element to another.

### HTML

    <div id="one" align="left">one</div>
    <div id="two">two</div>

### JavaScript

    let d1 = document.getElementById('one');
    let d2 = document.getElementById('two');
    let a = d1.getAttributeNode('align');

    d2.setAttributeNode(a.cloneNode(true));

    // Returns: 'left'
    alert(d2.attributes[1].value);

## Notes

If the attribute named already exists on the element, that attribute is replaced with the new one and the replaced one is returned.

This method is seldom used, with [`Element.setAttribute()`](setattribute) usually being used to change element's attributes.

DOM methods dealing with element's attributes:

<table><thead><tr class="header"><th>Not namespace-aware, most commonly used methods</th><th>Namespace-aware variants (DOM Level 2)</th><th>DOM Level 1 methods for dealing with <code>Attr</code> nodes directly (seldom used)</th><th>DOM Level 2 namespace-aware methods for dealing with <code>Attr</code> nodes directly (seldom used)</th></tr></thead><tbody><tr class="odd"><td><a href="setattribute"><code>setAttribute</code></a> (DOM 1)</td><td><a href="setattributens"><code>setAttributeNS</code></a></td><td><a href="setattributenode"><code>setAttributeNode</code></a></td><td><a href="setattributenodens"><code>setAttributeNodeNS</code></a></td></tr><tr class="even"><td><a href="getattribute"><code>getAttribute</code></a> (DOM 1)</td><td><a href="getattributens"><code>getAttributeNS</code></a></td><td><a href="getattributenode"><code>getAttributeNode</code></a></td><td><a href="getattributenodens"><code>getAttributeNodeNS</code></a></td></tr><tr class="odd"><td><a href="hasattribute"><code>hasAttribute</code></a> (DOM 2)</td><td><a href="hasattributens"><code>hasAttributeNS</code></a></td><td>-</td><td>-</td></tr><tr class="even"><td><a href="removeattribute"><code>removeAttribute</code></a> (DOM 1)</td><td><a href="removeattributens"><code>removeAttributeNS</code></a></td><td><a href="removeattributenode"><code>removeAttributeNode</code></a></td><td>-</td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-setattributenode">DOM<br />
<span class="small">The definition of 'setAttributeNode()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`setAttributeNode`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNode</a>
