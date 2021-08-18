# Document.xmlVersion

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Returns the version number as specified in the XML declaration (e.g., `<?xml version="1.0"?>`) or "1.0" if the declaration is absent.

This attribute was never really useful, since it always returned 1.0, and has been removed in DOM Level 4. As such, Firefox 10 no longer implements it. Its primary use in the past was to detect whether or not the document was being rendered as XML rather than HTML. To detect this, you can create an element with its name in lower case, then check to see if it gets converted into all upper case (in which case the document is in the non-XML HTML mode):

    if (document.createElement("foo").tagName == "FOO") {
      /* Document is not XML */
    }

## Specifications

- [http://www.w3.org/TR/DOM-Level-3-Cor...ument3-version](https://www.w3.org/TR/DOM-Level-3-Core/core.html#Document3-version)
- This has been removed from [DOM Core Level 4](https://www.w3.org/TR/domcore/)WD

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

`xmlVersion`

1

12

1-10

9

15

3

1

18

4-10

14

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/xmlVersion" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/xmlVersion</a>
