Encoding API
============

The **Encoding API** provides a mechanism for handling text in various [character encodings](https://developer.mozilla.org/en-US/docs/Glossary/character_encoding), including legacy non-[UTF-8](https://developer.mozilla.org/en-US/docs/Glossary/UTF-8) encodings.

The API provides four interfaces: [`TextDecoder`](textdecoder), [`TextEncoder`](textencoder), [`TextDecoderStream`](textdecoderstream) and [`TextEncoderStream`](textencoderstream).

**Note:** This feature is available in [Web Workers](web_workers_api).

Interfaces
----------

-   [`TextDecoder`](textdecoder)
-   [`TextEncoder`](textencoder)
-   [`TextDecoderStream`](textdecoderstream)
-   [`TextEncoderStream`](textencoderstream)

Polyfill
--------

-   A [shim](https://code.google.com/p/stringencoding/) allowing to use this interface in browsers that don't support it.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/">Encoding</a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Encoding_API`

38

79

19

18

Firefox 18 implemented an earlier and slightly different version of the specification.

No

25

10.1

38

38

19

18

Firefox 18 implemented an earlier and slightly different version of the specification.

Yes

10.3

3.0

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

`encode`

38

79

19

18

Firefox 18 implemented an earlier and slightly different version of the specification.

No

25

10.1

38

38

19

18

Firefox 18 implemented an earlier and slightly different version of the specification.

Yes

10.3

3.0

`encodeInto`

74

79

66

No

No

14.1

74

74

66

No

14.5

11.0

`encoding`

38

79

19

18

Firefox 18 implemented an earlier and slightly different version of the specification.

No

25

10.1

38

38

19

18

Firefox 18 implemented an earlier and slightly different version of the specification.

Yes

10.3

3.0

`worker_support`

38

79

20

No

25

10.1

38

38

20

?

10.3

3.0

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

`Encoding_API`

38

≤79

19

18

Implemented a slightly different version of the spec.

No

25

10.1

38

38

19

18

Implemented a slightly different version of the spec.

Yes

10.3

3.0

`TextDecoder`

38

≤79

19

18

Implemented a slightly different version of the spec.

No

25

10.1

38

38

19

18

Implemented a slightly different version of the spec.

?

10.3

3.0

`decode`

38

≤79

19

18

Implemented a slightly different version of the spec.

No

25

10.1

38

38

19

18

Implemented a slightly different version of the spec.

Yes

10.3

3.0

`encoding`

38

≤79

19

18

Implemented a slightly different version of the spec.

No

25

10.1

38

38

19

18

Implemented a slightly different version of the spec.

Yes

10.3

3.0

`fatal`

Yes

≤79

Yes

No

Yes

10.1

Yes

Yes

Yes

Yes

10.3

Yes

`ignoreBOM`

Yes

≤79

Yes

No

Yes

10.1

Yes

Yes

Yes

Yes

10.3

Yes

`worker_support`

38

≤79

20

No

25

10.1

38

38

20

?

10.3

3.0

BCD tables only load in the browser

### TextEncoder

BCD tables only load in the browser

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Encoding_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Encoding_API</a>
