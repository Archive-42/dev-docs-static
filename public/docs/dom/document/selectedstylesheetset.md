# Document.selectedStyleSheetSet

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `selectedStyleSheetSet` property <span class="seosummary">indicates the name of the style sheet set that's currently in use.</span>

## Syntax

    currentStyleSheetSet = document.selectedStyleSheetSet;

    document.selectedStyleSheet = newStyleSheetSet;

On return, `currentStyleSheetSet` indicates the name of the style sheet set currently in use. You can also set the current style sheet set using this property.

Setting the value of this property is equivalent to calling [`document.enableStyleSheetsForSet()`](enablestylesheetsforset) with the value of `currentStyleSheetSet`, then setting the value of `lastStyleSheetSet` to that value as well.

**Note:** This attribute's value is live; directly changing the `disabled` attribute on style sheets will affect the value of this attribute.

## Example

    console.log('Current style sheet set: ' + document.selectedStyleSheetSet);

    document.selectedStyleSheetSet = 'Some other style sheet';

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

`selectedStyleSheetSet`

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
- [`document.preferredStyleSheetSet`](preferredstylesheetset)
- [`document.styleSheetSets`](stylesheetsets)
- [`document.enableStyleSheetsForSet()`](enablestylesheetsforset)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/selectedStyleSheetSet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/selectedStyleSheetSet</a>
