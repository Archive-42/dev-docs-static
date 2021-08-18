Element.removeAttribute()
=========================

The [`Element`](../element) method `removeAttribute()` removes the attribute with the specified name from the element.

Syntax
------

    element.removeAttribute(attrName);

### Parameters

`attrName`  
A [`DOMString`](../domstring) specifying the name of the attribute to remove from the element. If the specified attribute does not exist, `removeAttribute()` returns without generating an error.

### Return value

`undefined`.

Usage notes
-----------

You should use `removeAttribute()` instead of setting the attribute value to `null` either directly or using [`setAttribute()`](setattribute). Many attributes will not behave as expected if you set them to `null`.

DOM methods dealing with element's attributes:

<table><thead><tr class="header"><th>Not namespace-aware, most commonly used methods</th><th>Namespace-aware variants (DOM Level 2)</th><th>DOM Level 1 methods for dealing with <code>Attr</code> nodes directly (seldom used)</th><th>DOM Level 2 namespace-aware methods for dealing with <code>Attr</code> nodes directly (seldom used)</th></tr></thead><tbody><tr class="odd"><td><a href="setattribute"><code>setAttribute</code></a> (DOM 1)</td><td><a href="setattributens"><code>setAttributeNS</code></a></td><td><a href="setattributenode"><code>setAttributeNode</code></a></td><td><a href="setattributenodens"><code>setAttributeNodeNS</code></a></td></tr><tr class="even"><td><a href="getattribute"><code>getAttribute</code></a> (DOM 1)</td><td><a href="getattributens"><code>getAttributeNS</code></a></td><td><a href="getattributenode"><code>getAttributeNode</code></a></td><td><a href="getattributenodens"><code>getAttributeNodeNS</code></a></td></tr><tr class="odd"><td><a href="hasattribute"><code>hasAttribute</code></a> (DOM 2)</td><td><a href="hasattributens"><code>hasAttributeNS</code></a></td><td>-</td><td>-</td></tr><tr class="even"><td><a href="removeattribute"><code>removeAttribute</code></a> (DOM 1)</td><td><a href="removeattributens"><code>removeAttributeNS</code></a></td><td><a href="removeattributenode"><code>removeAttributeNode</code></a></td><td>-</td></tr></tbody></table>

Example
-------

    // Given: <div id="div1" align="left" width="200px">
    document.getElementById("div1").removeAttribute("align");
    // Now: <div id="div1" width="200px">

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-removeattribute">DOM<br />
<span class="small">The definition of 'Element: removeAttribute' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`removeAttribute`

1

12

This function doesn't respect boolean attributes' default values. See [bug 12087679](https://developer.microsoft.com/microsoft-edge/platform/issues/12087679/).

1

5

8

1

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttribute" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttribute</a>
