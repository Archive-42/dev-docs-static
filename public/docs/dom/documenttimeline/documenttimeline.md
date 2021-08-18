# DocumentTimeline.DocumentTimeline()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `DocumentTimeline()` constructor of the [Web Animations API](../web_animations_api) creates a new instance of the [`DocumentTimeline`](../documenttimeline) object associated with the active document of the current browsing context.

## Syntax

    var sharedTimeline = new DocumentTimeline(options);

### Parameters

options  
An object specifying options for the new timeline. Currently the only supported option is the `originTime` member which specifies the zero time for the `documentTimeline` as a real number of milliseconds relative to the [`navigationStart`](../performancetiming/navigationstart) moment of the active document for the current browsing context.

## Examples

We could share a single `documentTimeline` among multiple animations, thus allowing us to manipulate just that group of animations via their shared timeline. This bit of code would start all the cats animating 500 milliseconds into their animations:

    var cats = document.querySelectorAll('.sharedTimelineCat');
    cats = Array.prototype.slice.call(cats);

    var sharedTimeline = new DocumentTimeline({ originTime: 500 });

    cats.forEach(function(cat) {
      var catKeyframes = new KeyframeEffect(cat, keyframes, timing);
      var catAnimation = new Animation(catKeyframes, sharedTimeline);
      catAnimation.play();
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-documenttimeline-documenttimeline">Web Animations<br />
<span class="small">The definition of 'DocumentTimeline()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

## See also

- [Web Animations API](../web_animations_api)
- [`AnimationTimeline`](../animationtimeline)
- [`DocumentTimeline`](../documenttimeline)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DocumentTimeline/DocumentTimeline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DocumentTimeline/DocumentTimeline</a>
