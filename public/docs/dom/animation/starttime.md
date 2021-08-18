# Animation.startTime

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Animation.startTime` property of the [`Animation`](../animation) interface is a double-precision floating-point value which indicates the scheduled time when an animation's playback should begin.

An animation’s **start time** is the time value of its <span class="page-not-created">`DocumentTimeline`</span> when its target [`KeyframeEffect`](../keyframeeffect) is scheduled to begin playback. An animation’s **start time** is initially unresolved (meaning that it's `null` because it has no value).

## Syntax

    var animationStartedWhen = Animation.startTime;

    Animation.startTime = newStartTime;

### Value

A floating-point number representing the current time in milliseconds, or `null` if no time is set. You can read this value to determine what the start time is currently set at, and you can change this value to make the animation start at a different time.

## Examples

In the [Running on Web Animations API example](https://codepen.io/rachelnabors/pen/zxYexJ?editors=0010), the we can sync all new animated cats by giving them all the same `startTime` as the original running cat:

    var catRunning = document.getElementById ("withWAAPI").animate(keyframes, timing);

    /* A function that makes new cats. */
    function addCat(){
      var newCat = document.createElement("div");
      newCat.classList.add("cat");
      return newCat;
    }

    /* This is the function that adds a cat to the WAAPI column */
    function animateNewCatWithWAAPI() {
      // make a new cat
      var newCat = addCat();

      // animate said cat with the WAAPI's "animate" function
      var newAnimationPlayer = newCat.animate(keyframes, timing);

      // set the animation's start time to be the same as the original .cat#withWAAPI
      newAnimationPlayer.startTime = catRunning.startTime;

      // Add the cat to the pile.
      WAAPICats.appendChild(newCat);
    }

## Reduced time precision

To offer protection against timing attacks and fingerprinting, the precision of `animation.startTime` might get rounded depending on browser settings.  
In Firefox, the `privacy.reduceTimerPrecision` preference is enabled by default and defaults to 20us in Firefox 59; in 60 it will be 2ms.

    // reduced time precision (2ms) in Firefox 60
    animation.startTime;
    // 23.404
    // 24.192
    // 25.514
    // ...

    // reduced time precision with `privacy.resistFingerprinting` enabled
    animation.startTime;
    // 49.8
    // 50.6
    // 51.7
    // ...

In Firefox, you can also enabled `privacy.resistFingerprinting`, the precision will be 100ms or the value of `privacy.resistFingerprinting.reduceTimerPrecision.microseconds`, whichever is larger.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-starttime">Web Animations<br />
<span class="small">The definition of 'Animation.startTime' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`startTime`

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

- [Web Animations API](../web_animations_api)
- [`Animation`](../animation)
- [`Animation.currentTime`](currenttime) for the current time of the animation.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/startTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/startTime</a>
