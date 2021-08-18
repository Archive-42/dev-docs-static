# HTMLAnchorElement.origin

The `HTMLAnchorElement.origin` read-only property is a [`USVString`](../usvstring) containing the Unicode serialization of the origin of the represented URL; that is:

- for URL using the `http` or `https`, the scheme followed by `'://'`, followed by the domain, followed by `':'`, followed by the port (the default port, `80` and `443` respectively, if explicitly specified);
- for URL using `file:` scheme, the value is browser dependant;
- for URL using the `blob:` scheme, the origin of the URL following `blob:`. E.g `"blob:https://mozilla.org"` will have `"https://mozilla.org".`

## Syntax

    // Getter
    string = anchor.origin;

    // No setter; read-only property

## Examples

    // An <a id="myAnchor" href="https://developer.mozilla.org/en-US/HTMLAnchorElement"> element is in the document
    const anchor = document.getElementById("myAnchor");
    anchor.origin; // returns 'https://developer.mozilla.org'

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-hyperlink-origin">HTML Living Standard<br />
<span class="small">The definition of 'HTMLHyperlinkElementUtils.origin' in that specification.</span></a></td></tr></tbody></table>

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

`origin`

8

17

26

Before Firefox 49, results for URL using the `blob` scheme incorrectly returned `null`.

No

15

5.1

≤37

18

26

Before Firefox 49, results for URL using the `blob` scheme incorrectly returned `null`.

14

5

1.0

## See also

- The [`HTMLAnchorElement`](../htmlanchorelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/origin</a>
