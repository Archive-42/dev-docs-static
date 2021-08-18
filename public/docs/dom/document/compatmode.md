# Document.compatMode

The `Document.compatMode` read-only property indicates whether the document is rendered in [Quirks mode](https://developer.mozilla.org/en-US/docs/Web/HTML/Quirks_Mode_and_Standards_Mode) or Standards mode.

## Syntax

    const mode = document.compatMode

### Value

An enumerated value that can be:

- "`BackCompat`" if the document is in quirks mode.
- "`CSS1Compat`" if the document is in no-quirks (also known as "standards") mode or limited-quirks (also known as "almost standards") mode.

**Note:** All these modes are now standardized, so the older "standards" and "almost standards" names are nonsensical and no longer used in standards.

## Example

    if (document.compatMode == "BackCompat") {
      // in Quirks mode
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-compatmode">DOM<br />
<span class="small">The definition of 'compatMode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`compatMode`

1

12

1

6

≤12.1

3.1

1

18

4

≤12.1

2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/compatMode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/compatMode</a>
