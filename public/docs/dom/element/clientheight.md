Element.clientHeight
====================

The `Element.clientHeight` read-only property is zero for elements with no CSS or inline layout boxes; otherwise, it's the inner height of an element in pixels. It includes padding but excludes borders, margins, and horizontal scrollbars (if present).

`clientHeight` can be calculated as: CSS `height` + CSS `padding` - height of horizontal scrollbar (if present).

When `clientHeight` is used on the root element (the `<html>` element), (or on `<body>` if the document is in quirks mode), the viewport's height (excluding any scrollbar) is returned. [This is a special case of `clientHeight`](https://www.w3.org/TR/2016/WD-cssom-view-1-20160317/#dom-element-clientheight).

**Note:** This property will round the value to an integer. If you need a fractional value, use [`element.getBoundingClientRect()`](getboundingclientrect).

Syntax
------

    var intElemClientHeight = element.clientHeight;

`intElemClientHeight` is an integer corresponding to the `clientHeight` of `element` in pixels. The `clientHeight` property is read–only.

Example
-------

<img src="data:image/png;base64,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" width="411" height="247" />

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-element-clientheight">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'clientHeight' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

### Notes

`clientHeight` is a property introduced in the Internet Explorer object model.

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

`clientHeight`

1

12

1

5

8

3

1

18

4

10.1

1

1.0

See also
--------

-   [`HTMLElement.offsetHeight`](../htmlelement/offsetheight)
-   [`Element.scrollHeight`](scrollheight)
-   [Determining the dimensions of elements](../css_object_model/determining_the_dimensions_of_elements)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/clientHeight" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/clientHeight</a>