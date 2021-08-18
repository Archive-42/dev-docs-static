# Document.hidden

The `Document.hidden` read-only property returns a Boolean value indicating if the page is considered hidden or not.

This property is described as "historical" in the [Page Visibility Level 2 specification](https://www.w3.org/TR/page-visibility-2/). Consider using the [`Document.visibilityState`](visibilitystate) property instead.

## Syntax

    var boolean = document.hidden

## Examples

    document.addEventListener("visibilitychange", function() {
      console.log( document.hidden );
      // Modify behavior...
    });

## Usage notes

Due to prerendering, it may happen that `document.hidden` is `true`, even if the page is actually visible to the user. In such scenario the page load starts with `document.visibilityState = "prerender"` and transitions to `document.visibilityState = "visible"` after some delay. This scenario can be reproduced by opening a new browser tab in Safari, pasting a URL in the URL bar, and navigating to that URL.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/page-visibility/#dom-document-hidden">Page Visibility (Second Edition)<br />
<span class="small">The definition of 'Document.hidden' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`hidden`

33

13

12

18

Since Firefox 56 it also returns `true` on Mac when the window is completely hidden by another non-translucent application.

10-52

10

12.1

6.1

4.4.3

≤37

33

Yes

18

Since Firefox 56 it also returns `true` on Mac when the window is completely hidden by another non-translucent application.

10-52

12.1

7

2.0

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/hidden" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/hidden</a>
