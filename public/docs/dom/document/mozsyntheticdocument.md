# Document.mozSyntheticDocument

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Document.mozSyntheticDocument` property indicates whether or not the document is a synthetic one; that is, a document representing a standalone image, video, audio, or the like.

## Syntax

    var isSynthetic = document.mozSyntheticDocument;

On return, `isSynthetic` is `true` if the document is a synthetic one; otherwise it's `false`.

## Example

This can be useful if you have a contextual menu item you only want to display for synthetic documents (or, conversely, for documents that aren't synthetic).

    var isSynthetic = document.mozSyntheticDocument;

    if (isSynthetic) {
      /* insert your menu item here */
    }

## Specifications

Not part of any specification.

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

`mozSyntheticDocument`

No

No

8-23

No

No

No

No

No

8-23

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/mozSyntheticDocument" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/mozSyntheticDocument</a>
