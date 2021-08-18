# KeyframeEffect.composite

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `composite` property of a [`KeyframeEffect`](../keyframeeffect) resolves how an element's animation impacts its underlying property values.

## Syntax

    // getting
    var compositeEnumeration = keyframeEffect.composite;

    // setting
    keyframeEffect.composite = 'accumulate';

### Value

To understand these values, take the example of a `keyframeEffect` value of `blur(2)` working on an underlying property value of `blur(3)`.

replace  
The `keyframeEffect` **overrides** the underlying value it is combined with: `blur(2) `replaces` blur(3)`.

add  
The `keyframeEffect` is **added** to the underlying value with which it is combined (aka _additive_): `blur(2) blur(3)`.

accumulate  
The keyframeEffect is **accumulated** on to the underlying value: `blur(5)`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-keyframeeffect-composite">Web Animations<br />
<span class="small">The definition of 'KeyframeEffect.composite' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`composite`

84

?

80

63-79

No

71

No

84

84

80

63-79

60

No

14.0

## See also

- [Web Animations API](../web_animations_api)
- Property of [`KeyframeEffect`](../keyframeeffect) objects.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect/composite" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect/composite</a>
