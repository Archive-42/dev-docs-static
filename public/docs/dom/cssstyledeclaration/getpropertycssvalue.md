# CSSStyleDeclaration.getPropertyCSSValue()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The **CSSStyleDeclaration.getPropertyCSSValue()** method interface returns a [`CSSValue`](../cssvalue) containing the CSS value for a property. Note that it returns `null` if the property name is a shorthand property.

You should use [`CSSStyleDeclaration.getPropertyValue()`](getpropertyvalue) instead.

## Syntax

    var value = style.getPropertyCSSValue(property);

### Parameters

- _`property`_ is a [`DOMString`](../domstring) representing the property name to be retrieved.

### Return value

- `value` is a [`CSSValue`](../cssvalue) containing the CSS value for a property. If none exists, returns `null`.

## Example

The following JavaScript code gets an object containing the computed RGB values of the `color` CSS property:

    var style = window.getComputedStyle(elem, null);
    var rgbObj = style.getPropertyCSSValue('color').getRGBColorValue();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSStyleDeclaration">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSStyleDeclaration' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Declared as obsolete in <a href="https://lists.w3.org/Archives/Public/www-style/2003Oct/0347.html">July 2003</a>.</td></tr></tbody></table>

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

`getPropertyCSSValue`

1-40

See [bug 331608](https://crbug.com/331608).

No

See [bug 331608](https://crbug.com/331608).

1-61

Only returns a result if called on the result of `getComputedStyle()`.

No

15-27

See [bug 331608](https://crbug.com/331608).

1

4.4-41

See [bug 331608](https://crbug.com/331608).

18-40

See [bug 331608](https://crbug.com/331608).

4-61

14-27

See [bug 331608](https://crbug.com/331608).

1

1.0-4.0

See [bug 331608](https://crbug.com/331608).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/getPropertyCSSValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/getPropertyCSSValue</a>
