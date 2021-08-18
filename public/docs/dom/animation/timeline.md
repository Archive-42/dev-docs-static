# Animation.timeline

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Animation.timeline` property of the [`Animation`](../animation) interface returns or sets the [`timeline`](../animationtimeline) associated with this animation. A timeline is a source of time values for synchronization purposes, and is an [`AnimationTimeline`](../animationtimeline)-based object. By default, the animation's timeline and the [`Document`](../document)'s timeline are the same.

## Syntax

    var animationsTimeline = Animation.timeline;

    Animation.timeline = newTimeline;

### Value

A [timeline object](../animationtimeline) to use as the timing source for the animation, or `null` to use the default, which is the [`Document`](../document)'s timeline.

## Examples

Here we set the animation's timeline to be the same as the document's timeline (this is the default timeline for all animations, by the way):

    animation.timeline = document.timeline;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-timeline">Web Animations<br />
<span class="small">The definition of 'Animation.timeline' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`timeline`

84

84

75

Currently only the getter is supported

No

70

13.1

Currently only the getter is supported

No

84

79

Currently only the getter is supported

60

13.4

Currently only the getter is supported

14.0

## See also

- [Web Animations API](../web_animations_api)
- [`Animation`](../animation)
- [`AnimationTimeline`](../animationtimeline) the parent object all timelines inherit from.
- [`DocumentTimeline`](../documenttimeline) the only kind of timeline object available at this time.
- [`Document.timeline`](../document/timeline) is the default timeline all animations are assigned.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/timeline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/timeline</a>
