# AnimationPlaybackEvent

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The AnimationPlaybackEvent interface of the [Web Animations API](web_animations_api) represents animation events.

As animations play, they report changes to their [`playState`](animation/playstate) through animation events.

## Constructor

[`AnimationPlaybackEvent.AnimationPlaybackEvent()`](animationplaybackevent/animationplaybackevent)  
Constructs a new `AnimationPlaybackEvent` object instance.

## Attributes

[`AnimationPlaybackEvent.currentTime`](animationplaybackevent/currenttime)  
The current time of the animation that generated the event.

[`AnimationPlaybackEvent.timelineTime`](animationplaybackevent/timelinetime)  
The time value of the timeline of the animation that generated the event.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#the-animationplaybackevent-interface">Web Animations<br />
<span class="small">The definition of 'AnimationPlaybackEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`AnimationPlaybackEvent`

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

`AnimationPlaybackEvent`

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

`currentTime`

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

- [Web Animations API](web_animations_api)
- [`Animation.playState`](animation/playstate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnimationPlaybackEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnimationPlaybackEvent</a>
