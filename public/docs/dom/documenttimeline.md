# DocumentTimeline

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `DocumentTimeline` interface of the [Web Animations API](web_animations_api) represents animation timelines, including the default document timeline (accessed via [`Document.timeline`](document/timeline)).

## Constructor

[`DocumentTimeline()`](documenttimeline/documenttimeline)  
Creates a new `DocumentTimeline` object associated with the active document of the current browsing context.

## Properties

_This interface inherits its property from its parent, [`AnimationTimeline`](animationtimeline)._

[`AnimationTimeline.currentTime`](animationtimeline/currenttime)  
Returns the time value in milliseconds for this timeline or `null` if it is inactive.

## Examples

We could share a single `documentTimeline` among multiple animations, thus allowing us to manipulate just that group of animations via their shared timeline. This bit of code would start all the cats animating 500 milliseconds into their animations:

    const cats = document.querySelectorAll('.sharedTimelineCat');
    const sharedTimeline = new DocumentTimeline({ originTime: 500 });

    for (const cat of cats) {
      const catKeyframes = new KeyframeEffect(cat, keyframes, timing);
      const catAnimation = new Animation(catKeyframes, sharedTimeline);
      catAnimation.play();
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#the-documenttimeline-interface">Web Animations<br />
<span class="small">The definition of 'DocumentTimeline' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`DocumentTimeline`

84

84

75

63-75

No

70

13.1

84

84

79

63-79

60

13.4

No

`DocumentTimeline`

84

84

75

63-75

No

70

13.1

84

84

79

63-79

60

13.4

No

## See also

- [Web Animations API](web_animations_api)
- [`AnimationTimeline`](animationtimeline)
- [`AnimationTimeline.currentTime`](animationtimeline/currenttime)
- [`Document.timeline`](document/timeline)
- [`DocumentTimeline.DocumentTimeline()`](documenttimeline/documenttimeline)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DocumentTimeline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DocumentTimeline</a>
