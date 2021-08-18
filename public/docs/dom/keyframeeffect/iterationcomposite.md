# KeyframeEffect.iterationComposite

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `iterationComposite` property of a [`KeyframeEffect`](../keyframeeffect) resolves how the animation's property value changes accumulate or override each other upon each of the animation's iterations.

## Syntax

    // getting
    var iterationCompositeEnumeration = keyframeEffect.iterationComposite;

    // setting
    keyframeEffect.iterationComposite = 'replace';

### Values

replace  
The `keyframeEffect` value produced is independent of the current iteration.

accumulate  
Subsequent iterations of the `keyframeEffect` build on the final value of the previous iteration.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-2/#dom-keyframeeffect-iterationcomposite">Web Animations Level 2<br />
<span class="small">The definition of 'iterationComposite' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`iterationComposite`

No

?

80

63-79

No

No

No

No

No

80

63-79

No

No

No

## See also

- [Web Animations API](../web_animations_api)
- Property of both [`KeyframeEffect`](../keyframeeffect) objects.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect/iterationComposite" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect/iterationComposite</a>
