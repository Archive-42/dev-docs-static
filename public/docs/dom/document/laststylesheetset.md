# Document.lastStyleSheetSet

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Document.lastStyleSheetSet` property <span class="seosummary">returns the last enabled style sheet set.</span> This property's value changes whenever the [`document.selectedStyleSheetSet`](selectedstylesheetset) property is changed.

## Syntax

    var lastStyleSheetSet = document.lastStyleSheetSet

On return, lastStyleSheetSet indicates the style sheet set that was most recently set. If the current style sheet set has not been changed by setting [`document.selectedStyleSheetSet`](selectedstylesheetset), the returned value is `null`.

**Note:** This value doesn't change when [`document.enableStyleSheetsForSet()`](enablestylesheetsforset) is called.

## Example

    let lastSheetSet = document.lastStyleSheetSet;

    if (!lastSheetSet) {
      lastSheetSet = 'Style sheet not yet changed';
    }
    else {
      console.log('The last style sheet set is: ' + lastSheetSet);
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

`lastStyleSheetSet`

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

- [`document.preferredStyleSheetSet`](preferredstylesheetset)
- [`document.selectedStyleSheetSet`](selectedstylesheetset)
- [`document.styleSheetSets`](stylesheetsets)
- [`document.enableStyleSheetsForSet()`](enablestylesheetsforset)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/lastStyleSheetSet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/lastStyleSheetSet</a>
