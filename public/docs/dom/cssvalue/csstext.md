# CSSValue.cssText

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `cssText` property of the [`CSSValue`](../cssvalue) interface represents the current computed CSS property value.

## Syntax

    cssText = cssValue.cssText;

### Value

A [`DOMString`](../domstring) representing the current CSS property value.

## Example

    var styleDeclaration = document.styleSheets[0].cssRules[0].style;
    var cssValue = styleDeclaration.getPropertyCSSValue("color");
    console.log(cssValue.cssText);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSValue-cssText">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSValue.cssText' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`cssText`

No

No

1-62

No

No

7

No

No

4-62

?

7

No

## See also

- [`CSSStyleDeclaration.getPropertyCSSValue()`](../cssstyledeclaration/getpropertycssvalue)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSValue/cssText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSValue/cssText</a>
