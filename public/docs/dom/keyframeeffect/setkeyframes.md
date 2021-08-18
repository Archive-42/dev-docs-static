KeyframeEffect.setKeyframes()
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `setKeyframes()` method of the [`KeyframeEffect`](../keyframeeffect) interface replaces the keyframes that make up the affected `KeyframeEffect` with a new set of keyframes.

Syntax
------

    existingKeyframeEffect.setKeyframes(keyframes);

Attributes
----------

### Parameters

keyframes  
<span style="line-height: 1.5;">A keyframe object or </span>`null`<span style="line-height: 1.5;">. If set to `null`, the keyframes are replaced with a sequence of empty keyframes.</span>  
  

There are two different ways to format keyframes:

1.  An `array` of objects (keyframes) consisting of properties and values to iterate over. This is the canonical format returned by the [`getKeyframes()`](getkeyframes) method.

        element.animate([
          { // from
            opacity: 0,
            color: "#fff"
          },
          { // to
            opacity: 1,
            color: "#000"
          }
        ], 2000);

    Offsets for each keyframe can be specified by providing an `offset` value.

        element.animate([ { opacity: 1 },
                          { opacity: 0.1, offset: 0.7 },
                          { opacity: 0 } ],
                        2000);

    **Note**: `offset` values, if provided, must be between 0.0 and 1.0 (inclusive) and arranged in ascending order.

    It is not necessary to specify an offset for every keyframe. Keyframes without a specified offset will be evenly spaced between adjacent keyframes.

    The easing to apply between keyframes can be specified by providing an `easing` value as illustrated below.

        element.animate([ { opacity: 1, easing: 'ease-out' },
                          { opacity: 0.1, easing: 'ease-in' },
                          { opacity: 0 } ],
                        2000);

    In this example, the specified easing only applies from the keyframe where it is specified until the next keyframe. Any `easing` value specified on the `options` argument, however, applies across a single iteration of the animation — for the entire duration.

2.  An `object` containing key-value pairs consisting of the property to animate and an `array` of values to iterate over.

        element.animate({
          opacity: [ 0, 1 ],          // [ from, to ]
          color:   [ "#fff", "#000" ] // [ from, to ]
        }, 2000);

    Using this format, the number of elements in each array does not need to be equal. The provided values will be spaced out independently.

        element.animate({
          opacity: [ 0, 1 ], // offset: 0, 1
          backgroundColor: [ "red", "yellow", "green" ], // offset: 0, 0.5, 1
        }, 2000);

    The special keys `offset`, `easing`, and `composite` (described below) may be specified alongside the property values.

        element.animate({
          opacity: [ 0, 0.9, 1 ],
          offset: [ 0, 0.8 ], // Shorthand for [ 0, 0.8, 1 ]
          easing: [ 'ease-in', 'ease-out' ],
        }, 2000);

    After generating a suitable set of keyframes from the property value lists, each supplied offset is applied to the corresponding keyframe. If there are insufficient values, or if the list contains `null` values, the keyframes without specified offsets will be evenly spaced as with the array format described above.

    If there are too few `easing` or `composite` values, the corresponding list will be repeated as needed.

### Implicit to/from keyframes

In newer browser versions, you are able to set a beginning or end state for an animation only (i.e. a single keyframe), and the browser will infer the other end of the animation if it is able to. For example, consider [this simple animation](https://mdn.github.io/dom-examples/web-animations-api/implicit-keyframes.html) — the Keyframe object looks like so:

    let rotate360 = [
      { transform: 'rotate(360deg)' }
    ];

We have only specified the end state of the animation, and the beginning state is implied.

Keyframes may specify property-value pairs for any of the [`animatable css properties`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties). The property names are specified using camel-case so for example [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) becomes `backgroundColor` and [`background-position-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-position-x) becomes `backgroundPositionX`. Shorthand values such as [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) are also permitted.

Two exceptional CSS properties are:

-   [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float), which must be written as `cssFloat` since "float" is a reserved word in JavaScript. It's just for reference here, this will have no effect on animation since "float" is not an animatable CSS property.
-   [`offset`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset), which must be written as `cssOffset` since "offset" represents the keyframe offset as described below.

The following special attributes may also be specified:

offset  
The offset of the keyframe specified as a number between `0.0` and `1.0` inclusive or `null`. This is equivalent to specifying start and end states in percentages in CSS stylesheets using `@keyframes`. If this value is `null` or missing, the keyframe will be evenly spaced between adjacent keyframes.

easing  
The [timing function](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function) used from this keyframe until the next keyframe in the series.

composite  
The [`KeyframeEffect.composite`](composite) operation used to combine the values specified in this keyframe with the underlying value. This will be `auto` if the composite operation specified on the effect is being used.

### Return value

Void.

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>TypeError</code></td><td>One or more of the frames were not of the correct type of object, the keyframes were not <a href="https://w3c.github.io/web-animations/#loosely-sorted-by-offset">loosely sorted by offset</a>, or a keyframe existed with an offset of less than 0 or more than 1.</td></tr></tbody></table>

**Note**: If the keyframes cannot be processed or are malformed, the `KeyframeEffect`'s keyframes are not modified.

Examples
--------

    // passing an array of keyframe objects
    existingKeyframeEffect.setKeyframes(
    [
      { color: 'blue' },
        { color: 'green', left: '10px' }
      ]
    );

    // passing an object with arrays for values
    existingKeyframeEffect.setKeyframes(
      {
        color: ['blue', 'green'],
        left: [ '0', '10px']
      }
    );

    // passing a single-member object
    existingKeyframeEffect.setKeyframes(
      {
        color: 'blue'
      }
    );

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-keyframeeffect-setkeyframes">Web Animations<br />
<span class="small">The definition of 'KeyframeEffect.setKeyframes()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`setKeyframes`

84

No

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

See also
--------

-   [KeyframeEffect Interface](../keyframeeffect)
-   [Web Animations API](../web_animations_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect/setKeyframes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect/setKeyframes</a>
