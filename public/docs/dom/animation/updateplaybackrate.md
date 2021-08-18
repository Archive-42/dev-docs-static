# Animation.updatePlaybackRate()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `updatePlaybackRate()`method of the [Web Animations API](../web_animations_api)'s [`Animation`](../animation) Interface sets the speed of an animation after first synchronizing its playback position.

In some cases, an animation may run on a separate thread or process and will continue updating even while long-running JavaScript delays the main thread. In such a case, setting the [`playbackRate`](playbackrate) on the animation directly may cause the animation's playback position to jump since its playback position on the main thread may have drifted from the playback position where it is currently running.

`updatePlaybackRate()` is an asynchronous method that sets the speed of an animation after synchronizing with its current playback position, ensuring that the resulting change in speed does not produce a sharp jump. After calling `updatePlaybackRate()` the animation's [`playbackRate`](playbackrate) is _not_ immediately updated. It will be updated once the animation's [`ready`](ready) promise is resolved.

## Syntax

    Animation.updatePlaybackRate(2);

### Parameters

playbackRate  
<span style="line-height: 1.5;">The new speed to set</span><span style="line-height: 1.5;">. This may be a positive number (to speed up or slow down the animation), a negative number (to make it play backwards), or zero (to effectively pause the animation).</span>

### Return value

None.

## Examples

A speed selector component would benefit from smooth updating of `updatePlaybackRate()`, as demonstrated below:

    speedSelector.addEventListener('input', evt => {
      cartoon.updatePlaybackRate(parseFloat(evt.target.value));
      cartoon.ready.then(() => {
        console.log(`Playback rate set to ${cartoon.playbackRate}`);
      });
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-updateplaybackrate">Web Animations<br />
<span class="small">The definition of 'updatePlaybackRate()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`updatePlaybackRate`

No

No

60

No

No

13.1

No

No

60

No

13.4

No

## See also

- [Web Animations API](../web_animations_api)
- [`Animation.playbackRate`](playbackrate) — read back the current playback rate or set it in a synchronous manner.
- [`Animation.reverse()`](reverse) — invert the playback rate and restart playback if necessary.
- [`Animation`](../animation) — contains other methods and properties you can use to control web page animation.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/updatePlaybackRate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/updatePlaybackRate</a>
