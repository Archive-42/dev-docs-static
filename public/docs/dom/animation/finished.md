# Animation.finished

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The ` Animation``.finished ` read-only property of the [Web Animations API](../web_animations_api) returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves once the animation has finished playing.

Every time the animation leaves the `finished` play state (that is, when it starts playing again), a new `Promise` is created for this property. The new `Promise` will resolve once the new animation sequence has completed.

## Syntax

    var animationsPromise = Animation.finished;

### Value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) object which will resolve once the animation has finished running.

## Examples

The following code waits until all animations running on the element `elem` have finished, then deletes the element from the DOM tree:

    Promise.all(
      elem.getAnimations().map(
        function(animation) {
          return animation.finished
        }
      )
    ).then(
      function() {
        return elem.remove();
      }
    );

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-finished">Web Animations<br />
<span class="small">The definition of 'Animation.finished' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`finished`

84

84

63

No

70

13.1

No

84

63

60

13.4

14.0

## See also

- [`KeyframeEffect`](../keyframeeffect)
- [Web Animations API](../web_animations_api)
- [`Animation`](../animation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/finished" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/finished</a>
