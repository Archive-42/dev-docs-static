# IntersectionObserverEntry.rootBounds

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`IntersectionObserverEntry`](../intersectionobserverentry) interface's read-only `rootBounds` property is a [`DOMRectReadOnly`](../domrectreadonly) corresponding to the [`target`](target)'s root intersection rectangle, offset by the [`IntersectionObserver.rootMargin`](../intersectionobserver/rootmargin) if one is specified.

## Syntax

    var rootBounds = IntersectionObserverEntry.rootBounds;

### Value

A [`DOMRectReadOnly`](../domrectreadonly) which describes the root intersection rectangle. For roots which are the [`Document`](../document)'s viewport, this rectangle is the bounds rectangle of the entire document. Otherwise, it's the bounds of the root element.

This rectangle is offset by the values in [`IntersectionObserver.rootMargin`](../intersectionobserver/rootmargin).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserverentry-rootbounds">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserverEntry.rootBounds' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`rootBounds`

51

15

55

No

Yes

12.1

51

51

55

?

12.2

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/rootBounds" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/rootBounds</a>
