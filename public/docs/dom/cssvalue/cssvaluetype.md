# CSSValue.cssValueType

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `cssValueType` read-only property of the [`CSSValue`](../cssvalue) interface represents the type of the current computed CSS property value.

## Syntax

    cssValueType = cssValue.cssValueType;

### Value

An `unsigned short` representing a code defining the type of the value. Possible values are:

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>CSS_CUSTOM</code></td><td>The value is a custom value.</td></tr><tr class="even"><td><code>CSS_INHERIT</code></td><td>The value is inherited and the <code>cssText</code> contains <code>"inherit"</code>.</td></tr><tr class="odd"><td><code>CSS_PRIMITIVE_VALUE</code></td><td>The value is a primitive value and an instance of the <a href="../cssprimitivevalue"><code>CSSPrimitiveValue</code></a> interface can be obtained by using binding-specific casting methods on this instance of the <code>CSSValue</code> interface.</td></tr><tr class="even"><td><code>CSS_VALUE_LIST</code></td><td>The value is a <code>CSSValue</code> list and an instance of the <a href="../cssvaluelist"><code>CSSValueList</code></a> interface can be obtained by using binding-specific casting methods on this instance of the <code>CSSValue</code> interface.</td></tr></tbody></table>

## Example

    var styleDeclaration = document.styleSheets[0].cssRules[0].style;
    var cssValue = styleDeclaration.getPropertyCSSValue("color");
    console.log(cssValue.cssValueType);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSValue-cssValueType">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSValue.cssValueType' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`cssValueType`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSValue/cssValueType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSValue/cssValueType</a>
