# Location: origin

The `origin` read-only property of the [`Location`](../location) interface is a [`USVString`](../usvstring) containing the Unicode serialization of the origin of the represented URL; that is:

- for URL using the `http` or `https`, the scheme followed by `'://'`, followed by the domain, followed by `':'`, followed by the port (the default port, `80` and `443` respectively, if explicitly specified);
- for URL using `file:` scheme, the value is browser dependant;
- for URL using the `blob:` scheme, the origin of the URL following `blob:`. E.g `"blob:https://mozilla.org"` will have `"https://mozilla.org".`

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    string = object.origin;

## Examples

    // On this page, returns the origin
    var result = window.location.origin; // Returns:'https://developer.mozilla.org'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-location-origin">HTML Living Standard<br />
<span class="small">The definition of 'origin' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

12

21

Before Firefox 49, results for URL using the blob scheme incorrectly returned null.

11

Intranet sites are set to Compatibility View, which will emulate IE7 and omit `window.location.origin`.

15

5.1

≤37

18

21

Before Firefox 49, results for URL using the blob scheme incorrectly returned null.

14

5

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/origin</a>
