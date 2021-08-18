# Document.fullscreen

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete [`Document`](../document) interface's `fullscreen` read-only property reports whether or not the document is currently displaying content in full-screen mode.

Although this property is read-only, it will not throw if it is modified (even in strict mode); the setter is a no-operation and it will be ignored.

**Note:** Since this property is deprecated, you can determine if full-screen mode is active on the document by checking to see if [`Document.fullscreenElement`](fullscreenelement) is not `null`.

## Syntax

    var isFullScreen = document.fullscreen;

### Value

A Boolean value which is `true` if the document is currently displaying an element in full-screen mode; otherwise, the value is `false.`

## Example

This simple function reports whether or not full-screen mode is currently active, using the obsolete `fullscreen` property.

    function isDocumentInFullScreenMode() {
      return document.fullscreen;
    }

This next example, on the other hand, uses the current `fullscreenElement` property to determine the same thing:

    function isDocumentInFullScreenMode() {
      return document.fullscreenElement !== null;
    }

If `fullscreenElement` isn't `null`, this returns `true`, indicating that full-screen mode is in effect.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/#dom-document-fullscreen">Fullscreen API<br />
<span class="small">The definition of 'Document.fullscreen' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition (as an obsolete property).</td></tr></tbody></table>

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

`fullscreen`

71

15

79

≤79

64

9

No

58

15

6

71

≤37

71

18

64

9

50

14

6

10.0

1.0

## See also

- [Fullscreen API](../fullscreen_api)
- [Guide to the Fullscreen API](../fullscreen_api/guide)
- [`Document.fullscreenEnabled`](fullscreenenabled)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreen</a>
