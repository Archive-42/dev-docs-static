# AnimationTimeline

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `AnimationTimeline` interface of the [Web Animations API](web_animations_api) represents the timeline of an animation. This interface exists to define timeline features (inherited by [`DocumentTimeline`](documenttimeline) and future timeline types) and is not itself directly used by developers. Anywhere you see `AnimationTimeline`, you should use `DocumentTimeline` or any other timeline type instead.

## Properties

[`AnimationTimeline.currentTime`](animationtimeline/currenttime) <span class="badge inline readonly">Read only </span>  
Returns the time value in milliseconds for this timeline or `null` if this timeline is inactive.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#the-animationtimeline-interface">Web Animations<br />
<span class="small">The definition of 'AnimationTimeline' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`AnimationTimeline`

84

84

75

63

No

70

13.1

No

84

79

63

60

13.4

14.0

`currentTime`

84

84

75

63

No

70

13.1

No

84

79

63

60

13.4

14.0

## See also

- [Web Animations API](web_animations_api)
- [`DocumentTimeline`](documenttimeline)
- [`Document.timeline`](document/timeline)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnimationTimeline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnimationTimeline</a>
