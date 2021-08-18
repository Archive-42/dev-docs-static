# Document.enableStyleSheetsForSet()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Enables the style sheets matching the specified name in the current style sheet set, and disables all other style sheets (except those without a title, which are always enabled).

## Syntax

    document.enableStyleSheetsForSet(name);

### Parameters

name  
The name of the style sheets to enable. All style sheets with a title that match this name will be enabled, while all others that have a title will be disabled. Specify an empty string for the name parameter to disable all alternate and preferred style sheets (but not the persistent style sheets; that is, those with no `title` attribute).

## Notes

- Title matches are case-sensitive.
- Calling this method with a `null` name has no effect; if you want to disable all alternate and preferred style sheets, you **must** pass "", the empty string.
- Stylesheets that don't have a title are never affected by this method.
- This method never affects the values of [`document.lastStyleSheetSet`](laststylesheetset) or [`document.preferredStyleSheetSet`](preferredstylesheetset).

## Example

    document.enableStyleSheetsForSet("Some style sheet set name");

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

`enableStyleSheetsForSet`

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

- [`Stylesheet`](../stylesheet)
- [`Document.styleSheets`](stylesheets)
- [`document.lastStyleSheetSet`](laststylesheetset)
- [`document.preferredStyleSheetSet`](preferredstylesheetset)
- [`document.selectedStyleSheetSet`](selectedstylesheetset)
- [`document.enableStyleSheetsForSet()`](enablestylesheetsforset)
- [Correctly Using Titles With External Stylesheets](https://developer.mozilla.org/en-US/docs/Archive/Web_Standards/Correctly_Using_Titles_With_External_Stylesheets)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/enableStyleSheetsForSet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/enableStyleSheetsForSet</a>
