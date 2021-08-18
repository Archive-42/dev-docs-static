TextDecoderStream.fatal
=======================

The `fatal` read-only property of the [`TextDecoderStream`](../textdecoderstream) interface is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the error mode of the `TextDecoderStream` object is set to `fatal`.

The two possible values of error mode are `fatal` or `replacement`, the default being `replacement` which pushes a replacement character `U+FFFD` (�) to the output.

Syntax
------

    var fatal = TextDecoderStream.fatal;

### Value

A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which will return `true` if the error mode is set to `fatal`. Otherwise it returns `false`.

Examples
--------

    stream = new TextDecoderStream();
    console.log(stream.fatal); // returns false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/#dom-textdecoder-fatal">Encoding<br />
<span class="small">The definition of 'TextDecoderStream.fatal' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextDecoderStream/fatal" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextDecoderStream/fatal</a>
