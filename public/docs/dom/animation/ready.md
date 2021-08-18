# Animation.ready

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `Animation.ready` property of the [Web Animations API](../web_animations_api) returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves when the animation is ready to play. A new promise is created every time the animation enters the `"pending"` [play state](playstate) as well as when the animation is canceled, since in both of those scenarios, the animation is ready to be started again.

Since the same [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is used for both pending `play` and pending `pause` requests, authors are advised to check the state of the animation when the promise is resolved.

## Syntax

    var readyPromise = Animation.ready;

### Value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves when the animation is ready to be played. You'll typically use a construct similar to this when using the ready promise:

    animation.ready.then(function() {
      // Do whatever needs to be done when
      // the animation is ready to run
    });

## Example

In the following example, the state of the animation will be `running` when the **current ready Promise** is resolved because the animation does not leave the `pending` play state in between the calls to `pause` and `play` and hence the **current ready Promise** does not change.

    animation.pause();
    animation.ready.then(function() {
      // Displays 'running'
      alert(animation.playState);
    });
    animation.play();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-ready">Web Animations<br />
<span class="small">The definition of 'Animation.ready' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`ready`

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

- [Web Animations API](../web_animations_api)
- [`Animation`](../animation)
- [`Animation.playState`](playstate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/ready" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/ready</a>
