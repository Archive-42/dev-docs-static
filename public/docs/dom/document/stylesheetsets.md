# Document.styleSheetSets

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `styleSheetSets` read-only property <span class="seosummary">returns a live list of all of the currently-available style sheet sets.</span>

## Syntax

    var sets = document.styleSheetSets;

On return, `sets` is a list of style sheet sets that are available.

## Example

Given an [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) (list) element with the ID "sheetList", you can populate it with the names of all the available style sheet sets with code like this:

    const list = document.getElementById('sheetList');
    const sheets = document.styleSheetSets;

    list.textContent = '';

    for (let i = 0; i < sheets.length; i++) {
      const item = document.createElement('li');

      item.textContent = sheets[i];
      list.appendChild(item);
    }

## Notes

The list of available style sheet sets is constructed by enumerating all the style sheets available for the document, in the order in which they're listed in the [`Document.styleSheets`](stylesheets) attribute, adding the `title` of each style sheet that has a title to the list. Duplicates are dropped from the list (using a case-sensitive comparison).

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

`styleSheetSets`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheetSets" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheetSets</a>
