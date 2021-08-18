# CSSPrimitiveValue.setStringValue()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `setStringValue()` method of the [`CSSPrimitiveValue`](../cssprimitivevalue) interface is used to set a string value. If the property attached to this value can't accept the specified unit or the string value, the value will be unchanged and a [`DOMException`](../domexception) will be raised.

## Syntax

    cssPrimitiveValue.setStringValue(stringType, stringValue);

### Parameters

stringType  
An `unsigned short` representing the type of the value. Possible values are:

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>CSS_ATTR</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/attr()"><code>attr()</code></a> function.</td></tr><tr class="even"><td><code>CSS_IDENT</code></td><td>The value is an identifier.</td></tr><tr class="odd"><td><code>CSS_STRING</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/string"><code>&lt;string&gt;</code></a>.</td></tr><tr class="even"><td><code>CSS_URI</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/url()"><code>url()</code></a>.</td></tr></tbody></table>

stringValue  
A [`DOMString`](../domstring) representing the new string value.

### Return value

Void.

### Exceptions

<table><thead><tr class="header"><th><strong>Type</strong></th><th><strong>Description</strong></th></tr></thead><tbody><tr class="odd"><td><code>DOMException</code></td><td>An <code>INVALID_ACCESS_ERR</code> is raised if the CSS value doesn't contain a string value or if the string value can't be converted into the specified unit.<br />
An NO_MODIFICATION_ALLOWED_ERR is raised if this property is read-only.</td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSPrimitiveValue-setStringValue">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSPrimitiveValue.setStringValue' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`setStringValue`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/setStringValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/setStringValue</a>
