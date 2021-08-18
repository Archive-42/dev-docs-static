# AnimationTimeline.currentTime

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `currentTime` read-only property of the [Web Animations API](../web_animations_api)'s [`AnimationTimeline`](../animationtimeline) interface returns the timeline's current time in milliseconds, or `null` if the timeline is inactive.

## Syntax

    var currentTime = AnimationTimeline.currentTime;

### Value

A number representing the timeline's current time in milliseconds, or `null` if the timeline is inactive.

## Reduced time precision

To offer protection against timing attacks and fingerprinting, the precision of `animationTimeline.currentTime` might get rounded depending on browser settings.  
In Firefox, the `privacy.reduceTimerPrecision` preference is enabled by default and defaults to 20us in Firefox 59; in 60 it will be 2ms.

    // reduced time precision (2ms) in Firefox 60
    animationTimeline.currentTime;
    // 23.404
    // 24.192
    // 25.514
    // ...

    // reduced time precision with `privacy.resistFingerprinting` enabled
    animationTimeline.currentTime;
    // 49.8
    // 50.6
    // 51.7
    // ...

In Firefox, you can also enable `privacy.resistFingerprinting`; the precision will be 100ms or the value of `privacy.resistFingerprinting.reduceTimerPrecision.microseconds`, whichever is larger.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animationtimeline-currenttime">Web Animations<br />
<span class="small">The definition of 'currentTime' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

84

84

75

63

No

70

13.1

No

84

79

63

60

13.4

14.0

## See also

- [Web Animations API](../web_animations_api)
- [`AnimationTimeline`](../animationtimeline)
- [`DocumentTimeline`](../documenttimeline) inherits this property
- [`Document.timeline`](../document/timeline) returns a timeline object which inherits this property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnimationTimeline/currentTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnimationTimeline/currentTime</a>
