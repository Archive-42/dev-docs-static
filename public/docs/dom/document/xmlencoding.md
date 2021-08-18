# Document.xmlEncoding

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Returns the encoding as determined by the XML declaration. Should be `null` if unspecified or unknown.

**Warning:** Do not use this attribute; it has been removed from the DOM Level 4 specification and is no longer supported in Gecko 10.0 (Firefox 10.0 / Thunderbird 10.0 / SeaMonkey 2.7).

If the XML Declaration states:

    <?xml version="1.0" encoding="UTF-16"?>

...the result should be "UTF-16".

However, Firefox 3.0 includes information on endianness (e.g., UTF-16BE for big endian encoding), and while this extra information is removed as of Firefox 3.1b3, Firefox 3.1b3 is still consulting the file's encoding, rather than the XML Declaration as the spec defines it ("An attribute specifying, <span class="underline">_as part of the XML declaration_</span>, the encoding of this document.").

## Specifications

- [http://www.w3.org/TR/DOM-Level-3-Cor...ment3-encoding](https://www.w3.org/TR/DOM-Level-3-Core/core.html#Document3-encoding)
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

`xmlEncoding`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/xmlEncoding" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/xmlEncoding</a>
