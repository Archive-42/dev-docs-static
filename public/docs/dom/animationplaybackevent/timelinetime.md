# AnimationPlaybackEvent.timelineTime

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `timelineTime` read-only property of the `AnimationPlaybackEvent` interface represents the time value of the animation's [`timeline`](../animationtimeline) at the moment the event is queued. This will be unresolved if the animation was not associated with a timeline at the time the event was generated or if the associated timeline was inactive.

## Value

A number representing the current time in milliseconds, or `null`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animationplaybackevent-timelinetime">Web Animations<br />
<span class="small">The definition of 'AnimationPlaybackEvent.timelineTime' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`timelineTime`

84

84

42

No

70

No

No

84

42

60

No

14.0

## See also

- [Web Animations API](../web_animations_api)
- [`AnimationPlayBackEvent`](../animationplaybackevent)
- [`AnimationTimeline`](../animationtimeline)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnimationPlaybackEvent/timelineTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnimationPlaybackEvent/timelineTime</a>
