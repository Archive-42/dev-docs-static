# CSSPrimitiveValue.getRectValue()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `getRectValue()` method of the [`CSSPrimitiveValue`](../cssprimitivevalue) interface is used to get a rect value. If this CSS value doesn't contain a rect value, a [`DOMException`](../domexception) is raised. Modification to the corresponding style property can be achieved using the <span class="page-not-created">`Rect`</span> interface.

## Syntax

    var rectValue = cssPrimitiveValue.getRectValue();

### Return value

A <span class="page-not-created">`Rect`</span> object representing the rect value.

### Exceptions

<table><thead><tr class="header"><th><strong>Type</strong></th><th><strong>Description</strong></th></tr></thead><tbody><tr class="odd"><td><code>DOMException</code></td><td>An <code>INVALID_ACCESS_ERR</code> is raised if the CSS value doesn't contain a Rect value. (i.e. this is not <code>CSS_RECT</code>).</td></tr></tbody></table>

## Example

    var cs = window.getComputedStyle(document.getElementById("clippedDiv"));
    var cssValue = cs.getPropertyCSSValue("clip");
    console.log(cssValue.getRectValue());

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSPrimitiveValue-getRectValue">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSPrimitiveValue.getRectValue' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`getRectValue`

1-40

No

20-62

No

15-27

3

1-40

18-40

20-62

14-27

1

1.0-4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getRectValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getRectValue</a>
