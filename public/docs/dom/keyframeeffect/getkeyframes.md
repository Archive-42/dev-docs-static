# KeyframeEffect.getKeyframes()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getKeyframes()` method of a [`KeyframeEffect`](../keyframeeffect) returns an Array of the computed keyframes that make up this animation along with their computed offsets.

## Syntax

    var keyframes = keyframeEffect.getKeyframes();

### Parameters

None.

### Return value

Returns a sequence of objects with the following format:

property value pairs  
As many property value pairs as are contained in each keyframe of the animation.

offset  
The offset of the keyframe specified as a number between `0.0` and `1.0` inclusive or `null`. This is equivalent to specifying start and end states in percentages in CSS stylesheets using `@keyframes`. This will be `null` if the keyframe is automatically spaced using `KeyframeEffect.spacing`.

computedOffset  
The computed offset for this keyframe, calculated when the list of computed keyframes was produced according to `KeyframeEffect.spacing`. Unlike `offset` above, the `computedOffset` is never `null`.

easing  
The [easing function](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function) used from this keyframe until the next keyframe in the series.

composite  
The [`KeyframeEffect.composite`](composite) operation used to combine the values specified in this keyframe with the underlying value. This will be absent if the composite operation specified on the effect is being used.

## Examples

In the [Red Queen Race](https://codepen.io/rachelnabors/pen/PNGGaV) example, we can inspect Alice and the RedQueen's animation to see its individual keyframes like so:

    // Return the array of keyframes

    redQueen_alice.effect.getKeyframes();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-keyframeeffect-getkeyframes">Web Animations<br />
<span class="small">The definition of 'KeyframeEffect.getKeyframes()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`getKeyframes`

84

?

63

No

71

No

84

84

63

60

No

14.0

## See also

- [Web Animations API](../web_animations_api)
- Method of [`KeyframeEffect`](../keyframeeffect) objects.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect/getKeyframes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect/getKeyframes</a>
