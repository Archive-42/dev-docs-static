Keyframe Formats
================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

[`Element.animate()`](../element/animate), [`KeyframeEffect.KeyframeEffect()`](../keyframeeffect/keyframeeffect), and [`KeyframeEffect.setKeyframes()`](../keyframeeffect/setkeyframes) all accept objects formatted to represent a set of keyframes. There are several options to this format, which are explained below.

Syntax
------

There are two different ways to format keyframes:

1.  An `array` of objects (keyframes) consisting of properties and values to iterate over. This is the canonical format returned by the [`getKeyframes()`](../keyframeeffect/getkeyframes) method.

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

Attributes
----------

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
The [`KeyframeEffect.composite`](../keyframeeffect/composite) operation used to combine the values specified in this keyframe with the underlying value. This will be `auto` if the composite operation specified on the effect is being used.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#processing-a-keyframes-argument">Web Animations<br />
<span class="small">The definition of 'Keyframe object formats' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`Keyframe_Formats`

36

79

48

No

23

13.1

Yes

37

36

48

24

13.4

3.0

`composite_option`

79

79

80

63-79

No

66

No

No

79

63-79

No

No

No

`id_option`

50

79

48

No

37

No

50

50

48

37

No

5.0

`implicit_tofrom`

No

Currently Chrome Canary only

No

75

No

No

13.1

Implementation seems somewhat buggy. More information will follow when available.

No

No

Currently Chrome Canary only

No

No

13.4

Implementation seems somewhat buggy. More information will follow when available.

No

`iterationcomposite_option`

No

No

80

63-79

No

No

No

No

No

63-79

No

No

No

`pseudoElement_option`

81

A valid animation object is returned but the targeted pseudoelement is not visually animated.

81

A valid animation object is returned but the targeted pseudoelement is not visually animated.

75

No

68

A valid animation object is returned but the targeted pseudoelement is not visually animated.

No

No

81

A valid animation object is returned but the targeted pseudoelement is not visually animated.

No

No

No

No

BCD tables only load in the browser

See also
--------

-   [Web Animations API](../web_animations_api)
-   [`Element.animate()`](../element/animate)
-   [`KeyframeEffect.KeyframeEffect()`](../keyframeeffect/keyframeeffect)
-   [`KeyframeEffect.setKeyframes()`](../keyframeeffect/setkeyframes)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API/Keyframe_Formats" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API/Keyframe_Formats</a>
