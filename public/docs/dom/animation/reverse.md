# Animation.reverse()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Animation.reverse()` method of the [`Animation`](../animation) Interface reverses the playback direction, meaning the animation ends at its beginning. If called on an unplayed animation, the whole animation is played backwards. If called on a paused animation, the animation will continue in reverse.

## Syntax

    animation.reverse();

### Parameters

None.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

## Example

In the [Growing/Shrinking Alice Game](https://codepen.io/rachelnabors/pen/PNYGZQ?editors=0010) example, clicking or tapping the bottle causes Alice's growing animation (`aliceChange`) to play backwards, causing her to get smaller. It is done by setting `aliceChange`'s [`Animation.playbackRate`](playbackrate) to `-1` like so:

    var shrinkAlice = function() {
      // play Alice's animation in reverse
      aliceChange.playbackRate = -1;
      aliceChange.play();

      // play the bottle's animation
      drinking.play()
    }

But it could also have been done by calling `reverse()` on `aliceChange` like so:

    var shrinkAlice = function() {
      // play Alice's animation in reverse
      aliceChange.reverse();

      // play the bottle's animation
      drinking.play()
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-reverse">Web Animations<br />
<span class="small">The definition of 'reverse()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`reverse`

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
- [`Animation.play()`](play) to move an animation forward.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/reverse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/reverse</a>
