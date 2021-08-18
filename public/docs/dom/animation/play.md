# Animation.play()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `play()` method of the [Web Animations API](../web_animations_api)'s [`Animation`](../animation) Interface starts or resumes playing of an animation. If the animation is finished, calling `play()` restarts the animation, playing it from the beginning.

## Syntax

    animation.play();

### Parameters

None.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

## Example

In the [Growing/Shrinking Alice Game](https://codepen.io/rachelnabors/pen/PNYGZQ?editors=0010) example, clicking or tapping the cake causes Alice's growing animation (`aliceChange`) to play forward, causing her to get bigger, as well as triggering the cake's animation. Two `Animation.play()`s, one `EventListener`:

    // The cake has its own animation:
    var nommingCake = document.getElementById('eat-me_sprite').animate(
    [
      { transform: 'translateY(0)' },
      { transform: 'translateY(-80%)' }
    ], {
      fill: 'forwards',
      easing: 'steps(4, end)',
      duration: aliceChange.effect.timing.duration / 2
    });

    // Pause the cake's animation so it doesn't play immediately.
    nommingCake.pause();

    // This function will play when ever a user clicks or taps
    var growAlice = function() {

      // Play Alice's animation.
      aliceChange.play();

      // Play the cake's animation.
      nommingCake.play();

    }

    // When a user holds their mouse down or taps, call growAlice to make all the animations play.
    cake.addEventListener("mousedown", growAlice, false);
    cake.addEventListener("touchstart", growAlice, false);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-play">Web Animations<br />
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

`play`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/play" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/play</a>
