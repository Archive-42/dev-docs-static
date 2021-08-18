# Animation.playbackRate

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The ` Animation``.playbackRate ` property of the [Web Animations API](../web_animations_api) returns or sets the playback rate of the animation.

Animations have a **playback rate** that provides a scaling factor from the rate of change of the animation's [`timeline`](../documenttimeline) time values to the animation’s current time. The playback rate is initially `1`.

## Syntax

    var currentPlaybackRate = Animation.playbackRate;

    Animation.playbackRate = newRate;

### Value

Takes a number that can be 0, negative, or positive. Negative values reverse the animation. The value is a scaling factor, so for example a value of 2 would double the playback rate.

Setting an animation’s `playbackRate` to `0` effectively pauses the animation (however, its [`playstate`](playstate) does not necessarily become `paused`).

## Examples

In the [Growing/Shrinking Alice Game](https://codepen.io/rachelnabors/pen/PNYGZQ?editors=0010) example, clicking or tapping the bottle causes Alice's growing animation (`aliceChange`) to reverse, causing her to shrink:

    var shrinkAlice = function() {
      aliceChange.playbackRate = -1;
      aliceChange.play();
    }

    // On tap or click, Alice will shrink.
    bottle.addEventListener("mousedown", shrinkAlice, false);
    bottle.addEventListener("touchstart", shrinkAlice, false);

Contrariwise, clicking on the cake causes her to "grow," playing `aliceChange` forwards again:

    var growAlice = function() {
      aliceChange.playbackRate = 1;
      aliceChange.play();
    }

    // On tap or click, Alice will grow.
    cake.addEventListener("mousedown", growAlice, false);
    cake.addEventListener("touchstart", growAlice, false);

In another example, the [Red Queen's Race Game](https://codepen.io/rachelnabors/pen/PNGGaV?editors=0010), Alice and the Red Queen are constantly slowing down:

    setInterval( function() {

      // Make sure the playback rate never falls below .4

      if (redQueen_alice.playbackRate > .4) {
        redQueen_alice.playbackRate *= .9;
      }

    }, 3000);

But clicking or tapping on them causes them to speed up by multiplying their `playbackRate`:

    var goFaster = function() {
      redQueen_alice.playbackRate *= 1.1;
    }

    document.addEventListener("click", goFaster);
    document.addEventListener("touchstart", goFaster);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-playbackrate">Web Animations<br />
<span class="small">The definition of 'Animation.playbackRate' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`playbackRate`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/playbackRate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/playbackRate</a>
