# CSSPositionValue.x

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `x` property of the [`CSSPositionValue`](../csspositionvalue) interface returns the item's position along the web page's horizontal axis.

## Syntax

    var x = CSSPositionValue.x

### Value

A [`CSSNumericValue`](../cssnumericvalue).

## Example

The following example positions a container `<div>` 5 pixels from the top and 10 pixels from the left of the page.

    let someDiv = document.getElementById('container');
    let position = new CSSPositionValue(CSS.px(5), CSS.px(10));

    someDiv.attributeStyleMap.set('object-position', position);
    console.log(position.x.value, position.y.value);

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

`x`

66

79

No

No

53

No

66

66

No

47

No

9.0

## See also

- [`CSSPositionValue.CSSPositionValue()`](csspositionvalue)
- [`CSSPositionValue.y`](y)
- [Using the CSS Typed OM](../css_typed_om_api/guide)
- [CSS Typed Object Model API](../css_typed_om_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPositionValue/x" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPositionValue/x</a>
