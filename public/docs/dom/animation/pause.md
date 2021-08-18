# Animation.pause()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `pause()` method of the [Web Animations API](../web_animations_api)'s [`Animation`](../animation) interface suspends playback of the animation.

## Syntax

    animation.pause();

### Parameters

None.

### Return value

None.

### Exceptions

InvalidStateError  
The animation's [`currentTime`](currenttime) is `unresolved` (for example, if it's never been played or isn't currently playing) and the end time of the animation is positive infinity.

Throws an `InvalidStateError` if the animation's [`currentTime`](currenttime) is `unresolved` (perhaps it hasn't started playing yet) and the end time of the animation is positive infinity.

## Example

`Animation.pause()` is used many times in the Alice in Web Animations API Land [Growing/Shrinking Alice Game](https://codepen.io/rachelnabors/pen/PNYGZQ?editors=0010), largely because animations created with the [`Element.animate()`](../element/animate) method immediately start playing and must be paused manually if you want to avoid that:

    // animation of the cupcake slowly getting eaten up
    var nommingCake = document.getElementById('eat-me_sprite').animate(
    [
      { transform: 'translateY(0)' },
      { transform: 'translateY(-80%)' }
    ], {
      fill: 'forwards',
      easing: 'steps(4, end)',
      duration: aliceChange.effect.timing.duration / 2
    });

    // doesn't actually need to be eaten until a click event, so pause it initially:
    nommingCake.pause();

Additionally, when resetting :

    // An all-purpose function to pause the animations on Alice, the cupcake, and the bottle that reads "drink me."
    var stopPlayingAlice = function() {
      aliceChange.pause();
      nommingCake.pause();
      drinking.pause();
    };

    // When the user releases the cupcake or the bottle, pause the animations.
    cake.addEventListener("mouseup", stopPlayingAlice, false);
    bottle.addEventListener("mouseup", stopPlayingAlice, false);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-pause">Web Animations<br />
<span class="small">The definition of 'play()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`pause`

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
- [`Animation`](../animation) for other methods and properties you can use to control web page animation.
- [`Animation.pause()`](pause) to pause an animation.
- [`Animation.reverse()`](reverse) to play an animation backwards.
- [`Animation.finish()`](finish) to finish an animation.
- [`Animation.cancel()`](cancel) to cancel an animation.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/pause" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/pause</a>
