TextEncoder()
=============

The `TextEncoder()` constructor returns a newly created utf-8 [`TextEncoder`](../textencoder) object.

Syntax
------

    encoder = new TextEncoder();

### Parameters

-   `TextEncoder()` takes no parameters since Firefox 48 and Chrome 53

**Note**: Prior to Firefox 48 and Chrome 53, an encoding type label was accepted as a paramer to the `TextEncoder` object, since then both browsers have removed support for any encoder type other than `utf-8`, to match the [spec](https://www.w3.org/TR/encoding/#dom-textencoder). Any type label passed into the `TextEncoder` constructor will now be ignored and a `utf-8` `TextEncoder` will be created.

### Exceptions

-   `TextEncoder()` throws no exceptions since Firefox 48 and Chrome 53

**Note**: Prior to Firefox 48 and Chrome 53 an exception would be thrown for an unknown encoding type.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/#dom-textencoder">Encoding<br />
<span class="small">The definition of 'TextEncoder()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

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

`TextEncoder`

53

Does not accept parameters. Supports only `utf-8` encoding.

38-53

Throws `RangeError` exception for unknown encoding types.

79

Does not accept parameters. Supports only `utf-8` encoding.

48

The constructor accepts an encoding type label argument, but the value is ignored. Only `utf-8` encoding is supported.

38-48

If the encoding type label argument is invalid, then a `RangeError` exception is thrown.

19-38

If the encoding type label argument is invalid, then a `TypeError` exception is thrown.

18

Firefox 18 implemented an earlier and slightly different version of the specification.

No

25

10.1

38

38

48

The constructor accepts an encoding type label argument, but the value is ignored. Only `utf-8` encoding is supported.

38-48

If the encoding type label argument is invalid, then a `RangeError` exception is thrown.

19-38

If the encoding type label argument is invalid, then a `TypeError` exception is thrown.

18

Firefox 18 implemented an earlier and slightly different version of the specification.

?

10.3

3.0

See also
--------

-   The [`TextEncoder`](../textencoder) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextEncoder/TextEncoder" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextEncoder/TextEncoder</a>
