# Animation.currentTime

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The ` Animation``.currentTime ` property of the [Web Animations API](../web_animations_api) returns and sets the current time value of the animation in milliseconds, whether running or paused.

If the animation lacks a [`timeline`](../animationtimeline), is inactive, or hasn't been played yet, `currentTime`'s return value is `null`.

## Syntax

    var currentTime = Animation.currentTime;
    Animation.currentTime = newTime;

### Value

A number representing the current time in milliseconds, or `null` to deactivate the animation.

## Examples

In the [Drink Me/Eat Me game](https://codepen.io/rachelnabors/pen/PNYGZQ?editors=0010), Alice's height is animated so it can go from small to large or large to small. At the start of the game, her height is set between the two extremes by setting her animation's `currentTime` to half her [`KeyframeEffect`'s duration](../effecttiming):

    aliceChange.currentTime = aliceChange.effect.timing.duration / 2;

A more generic means of seeking to the 50% mark of an animation would be:

    animation.currentTime =
      animation.effect.getComputedTiming().delay +
      animation.effect.getComputedTiming().activeDuration / 2;

## Reduced time precision

To offer protection against timing attacks and fingerprinting, the precision of `animation.currentTime` might get rounded depending on browser settings.  
In Firefox, the `privacy.reduceTimerPrecision` preference is enabled by default and defaults to 20us in Firefox 59; in 60 it will be 2ms.

    // reduced time precision (2ms) in Firefox 60
    animation.currentTime;
    // 23.404
    // 24.192
    // 25.514
    // ...

    // reduced time precision with `privacy.resistFingerprinting` enabled
    animation.currentTime;
    // 49.8
    // 50.6
    // 51.7
    // ...

In Firefox, you can also enabled `privacy.resistFingerprinting`, the precision will be 100ms or the value of `privacy.resistFingerprinting.reduceTimerPrecision.microseconds`, whichever is larger.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-currenttime">Web Animations<br />
<span class="small">The definition of 'currentTime' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`currentTime`

39

79

48

No

26

13.1

39

39

48

26

13.4

4.0

## See also

- [`Animation`](../animation) for other methods and properties you can use to control web page animation.
- [`Animation.startTime`](starttime) for the time an animation is scheduled to start.
- [Web Animations API](../web_animations_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/currentTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/currentTime</a>
