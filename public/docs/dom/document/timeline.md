# Document.timeline

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `timeline` readonly property of the [`Document`](../document) interface represents the default timeline of the current document. This timeline is a special instance of [`DocumentTimeline`](../documenttimeline) that is automatically created on page load.

This timeline is unique to each `document` and persists for the lifetime of the `document` including calls to [`Document.open()`](open).

The time values for this timeline are calculated as a fixed offset from the global clock such that the **zero time** corresponds to the [`navigationStart`](../performancetiming/navigationstart) moment plus a signed delta known as the **origin time.** Prior to establishing the `navigationStart` moment, the document timeline is **inactive**.

**Note**: A document timeline that is associated with a non-active document is also considered to be **inactive**.

## Syntax

    var pageTimeline = document.timeline;
    var thisMoment = pageTimeline.currentTime;

### Value

A [`DocumentTimeline`](../documenttimeline) object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-document-timeline">Web Animations<br />
<span class="small">The definition of 'document.timeline' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

No

70

13.1

84

84

79

63-79

60

13.4

14.0

## See also

- [Web Animations API](../web_animations_api)
- [`AnimationTimeline`](../animationtimeline)
- [`AnimationTimeline.currentTime`](../animationtimeline/currenttime)
- [`DocumentTimeline`](../documenttimeline)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/timeline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/timeline</a>
