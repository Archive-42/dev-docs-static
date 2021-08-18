TextDecoderStream
=================

The `TextDecoderStream` interface of the [Encoding API](encoding_api) converts a stream of strings into bytes in the UTF-8 encoding. It is the streaming equivalent of [`TextDecoder`](textdecoder).

Constructor
-----------

[`TextDecoderStream.TextDecoderStream()`](textdecoderstream/textdecoderstream)  
Creates a new `TextDecoderStream` object.

Properties
----------

 [`TextDecoderStream.encoding`](textdecoderstream/encoding)<span class="badge inline readonly">Read only </span>   
An encoding.

 [`TextDecoderStream.fatal`](textdecoderstream/fatal)<span class="badge inline readonly">Read only </span>   
A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the error mode is fatal.

 [`TextDecoderStream.ignoreBOM`](textdecoderstream/ignorebom)<span class="badge inline readonly">Read only </span>   
A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the byte order mark is ignored.

 [`TextDecoderStream.readable`](textdecoderstream/readable)<span class="badge inline readonly">Read only </span>   
Returns the [`ReadableStream`](readablestream) instance controlled by this object.

 [`TextDecoderStream.writable`](textdecoderstream/writable)<span class="badge inline readonly">Read only </span>   
Returns the [`WritableStream`](writablestream) instance controlled by this object.

Examples
--------

-   [Examples of streaming structured data and HTML](https://streams.spec.whatwg.org/demos/)
-   [An example of fetch request streams which uses `TextDecoderStream`](https://glitch.com/~fetch-request-stream).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/#interface-TextDecoderStream">Encoding<br />
<span class="small">The definition of 'TextDecoderStream' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TextDecoderStream`

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

`TextDecoderStream`

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

`fatal`

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

`ignoreBOM`

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

-   [`TextEncoderStream`](textencoderstream)
-   [Streams API Concepts](streams_api/concepts)
-   [Experimenting with the Streams API](https://deanhume.com/experimenting-with-the-streams-api/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextDecoderStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextDecoderStream</a>
