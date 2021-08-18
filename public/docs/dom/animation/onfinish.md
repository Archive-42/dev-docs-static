# Animation.onfinish

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`Animation`](../animation) interface's `onfinish` property (from the [Web Animations API](../web_animations_api)) is the event handler for the `finish` event. This event is sent when the animation finishes playing.

The `finish` event occurs when the animation completes naturally, as well as when the [`Animation.finish()`](finish) method is called to immediately cause the animation to finish up.

The `"paused"` play state supersedes the `"finished"` play state; if the animation is both paused and finished, the `"paused"` state is the one that will be reported. You can force the animation into the `"finished"` state by setting its [`startTime`](starttime) to `document.timeline.currentTime - (Animation.currentTime * Animation.playbackRate)`.

## Syntax

    var finishHandler = Animation.onfinish;

    Animation.onfinish = finishHandler;

### Value

A function to be called to handle the `finish` event, or `null` if no `finish` event handler is set.

## Examples

`Animation.onfinish` is used several times in the Alice in Web Animations API Land [Growing/Shrinking Alice Game](https://codepen.io/rachelnabors/pen/PNYGZQ?editors=0010). Here is one instance where we add pointer events back to an element after its opacity animation has faded it in:

    // Add an animation to the game's ending credits
    var endingUI = document.getElementById("ending-ui");
    var bringUI = endingUI.animate(keysFade, timingFade);

    // Pause said animation's credits
    bringUI.pause();

    // This function removes pointer events on the credits.
    hide(endingUI);

    // When the credits are later faded in,
    // we re-add the pointer events when they're done
    bringUI.onfinish = function() {
      endingUI.style.pointerEvents = 'auto';
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-onfinish">Web Animations<br />
<span class="small">The definition of 'Animation.onfinish' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`onfinish`

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
- [`Animation.finish()`](finish)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/onfinish" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/onfinish</a>
