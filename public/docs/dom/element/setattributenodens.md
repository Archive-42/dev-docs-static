# Element.setAttributeNodeNS()

`setAttributeNodeNS` adds a new namespaced attribute node to an element.

## Syntax

    replacedAttr = element.setAttributeNodeNS(attributeNode)

- `replacedAttr` is the replaced attribute node, if any, returned by this function.
- `attributeNode` is an `Attr` node.

## Example

    // <div id="one" xmlns:myNS="http://www.mozilla.org/ns/specialspace"
    //            myNS:special-align="utterleft">one</div>
    // <div id="two">two</div>

    var myns = "http://www.mozilla.org/ns/specialspace";
    var d1 = document.getElementById("one");
    var d2 = document.getElementById("two");
    var a = d1.getAttributeNodeNS(myns, "special-align");
    d2.setAttributeNodeNS(a.cloneNode(true));
    alert(d2.attributes[1].value) // returns: `utterleft'

## Notes

If the specified attribute already exists on the element, then that attribute is replaced with the new one and the replaced one is returned.

Note that if you try to set without cloning the node, Mozilla gives an NS_ERROR_DOM_INUSE_ATTRIBUTE_ERR "Attribute already in use" error, as the DOM requires cloning for Attr to be reused (unlike other Nodes which can be moved).

DOM methods dealing with element's attributes:

<table><thead><tr class="header"><th>Not namespace-aware, most commonly used methods</th><th>Namespace-aware variants (DOM Level 2)</th><th>DOM Level 1 methods for dealing with <code>Attr</code> nodes directly (seldom used)</th><th>DOM Level 2 namespace-aware methods for dealing with <code>Attr</code> nodes directly (seldom used)</th></tr></thead><tbody><tr class="odd"><td><a href="setattribute"><code>setAttribute</code></a> (DOM 1)</td><td><a href="setattributens"><code>setAttributeNS</code></a></td><td><a href="setattributenode"><code>setAttributeNode</code></a></td><td><a href="setattributenodens"><code>setAttributeNodeNS</code></a></td></tr><tr class="even"><td><a href="getattribute"><code>getAttribute</code></a> (DOM 1)</td><td><a href="getattributens"><code>getAttributeNS</code></a></td><td><a href="getattributenode"><code>getAttributeNode</code></a></td><td><a href="getattributenodens"><code>getAttributeNodeNS</code></a></td></tr><tr class="odd"><td><a href="hasattribute"><code>hasAttribute</code></a> (DOM 2)</td><td><a href="hasattributens"><code>hasAttributeNS</code></a></td><td>-</td><td>-</td></tr><tr class="even"><td><a href="removeattribute"><code>removeAttribute</code></a> (DOM 1)</td><td><a href="removeattributens"><code>removeAttributeNS</code></a></td><td><a href="removeattributenode"><code>removeAttributeNode</code></a></td><td>-</td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-setattributenodens">DOM<br />
<span class="small">The definition of 'document.setAttributeNodeNS' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`setAttributeNodeNS`

1

12

Returns a `ClientRectList` with [ClientRect](<http://msdn.microsoft.com/en-us/library/hh826029(VS.85).aspx>) objects (which do not contain `x` and `y` properties) instead of [`DOMRect`](https://developer.mozilla.org/docs/Web/API/DOMRect) objects.

1

9

Returns a `ClientRectList` with [ClientRect](<http://msdn.microsoft.com/en-us/library/hh826029(VS.85).aspx>) objects (which do not contain `x` and `y` properties) instead of [`DOMRect`](https://developer.mozilla.org/docs/Web/API/DOMRect) objects.

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNodeNS" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNodeNS</a>
