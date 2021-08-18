# Animation.finish()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `finish()`method of the [Web Animations API](../web_animations_api)'s [`Animation`](../animation) Interface sets the current playback time to the end of the animation corresponding to the current playback direction. That is, if the animation is playing forward, it sets the playback time to the length of the animation sequence, and if the animation is playing in reverse (having had its [`reverse()`](reverse) method called), it sets the playback time to 0.

## Syntax

    Animation.finish();

### Parameters

None.

### Return value

None.

### Exceptions

`InvalidState`  
The player's playback rate is 0 or the animation's playback rate is greater than 0 and the end time of the animation is infinity.

## Examples

The following example shows how to use the `finish()` method and catch an `InvalidState` error.

    interfaceElement.addEventListener("mousedown", function() {
      try {
        player.finish();
      } catch(e if e instanceof InvalidState) {
        console.log("finish() called on paused or finished animation.");
      } catch(e);
        logMyErrors(e); //pass exception object to error handler
      }
    });

The following example finishes all the animations on a single element, regardless of their direction of playback.

    elem.getAnimations().forEach(
      function(animation){
        return animation.finish();
      }
    );

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-finish">Web Animations<br />
<span class="small">The definition of 'finish()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`finish`

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
- [`Animation.play()`](play) to play an animation forward.
- [`Animation.reverse()`](reverse) to play an animation backward.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/finish" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/finish</a>
