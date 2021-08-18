# Document.preferredStyleSheetSet

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `preferredStyleSheetSet` property <span class="seosummary">returns the preferred style sheet set as set by the page author.</span>

## Syntax

    preferredStyleSheetSet = document.preferredStyleSheetSet

On return, `preferredStyleSheetSet` indicates the author's preferred style sheet set. This is determined from the order of style sheet declarations and the `Default-Style` HTTP header.

If there isn't a preferred style sheet set defined by the author, the empty string (`""`) is returned.

## Example

    if (document.preferredStyleSheetSet) {
      console.log("The preferred style sheet set is: " + document.preferredStyleSheetSet);
    } else {
      console.log("There is no preferred style sheet.");
    }

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

`preferredStyleSheetSet`

No

No

3

No

No

No

No

No

4

No

No

No

## See also

- [`document.lastStyleSheetSet`](laststylesheetset)
- [`document.selectedStyleSheetSet`](selectedstylesheetset)
- [`document.styleSheetSets`](stylesheetsets)
- [`document.enableStyleSheetsForSet()`](enablestylesheetsforset)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/preferredStyleSheetSet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/preferredStyleSheetSet</a>
