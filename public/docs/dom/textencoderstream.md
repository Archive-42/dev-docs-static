TextEncoderStream
=================

The `TextEncoderStream` interface of the [Encoding API](encoding_api) converts a stream of strings into bytes in the UTF-8 encoding. It is the streaming equivalent of [`TextEncoder`](textencoder).

Constructor
-----------

[`TextEncoderStream.TextEncoderStream()`](textencoderstream/textencoderstream)  
Creates a new `TextEncoderStream` object.

Properties
----------

 [`TextEncoderStream.encoding`](textencoderstream/encoding)<span class="badge inline readonly">Read only </span>   
Always returns "`utf-8`".

 [`TextEncoderStream.readable`](textencoderstream/readable)<span class="badge inline readonly">Read only </span>   
Returns the [`ReadableStream`](readablestream) instance controlled by this object.

 [`TextEncoderStream.writable`](textencoderstream/writable)<span class="badge inline readonly">Read only </span>   
Returns the [`WritableStream`](writablestream) instance controlled by this object.

Examples
--------

-   [Examples of streaming structured data and HTML](https://streams.spec.whatwg.org/demos/)
-   [An example of fetch request streams which uses `TextEncoderStream` to upload the data](https://glitch.com/~fetch-request-stream).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/#interface-textencoderstream">Encoding<br />
<span class="small">The definition of 'TextEncoderStream' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TextEncoderStream`

71

79

No

No

58

14.1

71

71

No

50

14.5

10.0

`TextEncoderStream`

71

79

No

No

58

14.1

71

71

No

50

14.5

10.0

`encoding`

71

79

No

No

58

14.1

71

71

No

50

14.5

10.0

`readable`

71

79

No

No

58

14.1

71

71

No

50

14.5

10.0

`writable`

71

79

No

No

58

14.1

71

71

No

50

14.5

10.0

See also
--------

-   [`TextDecoderStream`](textdecoderstream)
-   [Streams API Concepts](streams_api/concepts)
-   [Experimenting with the Streams API](https://deanhume.com/experimenting-with-the-streams-api/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextEncoderStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextEncoderStream</a>
