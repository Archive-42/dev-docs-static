TextEncoder.prototype.encode()
==============================

The `TextEncoder.prototype.encode()` method takes a [`USVString`](../usvstring) as input, and returns a [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) containing the text given in parameters encoded with the specific method for that `TextEncoder` object.

Syntax
------

    b1 = encoder.encode(string);

### Parameters

`string`  
Is a [`USVString`](../usvstring) containing the text to encode.

### Return value

A [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) object.

Examples
--------

    <p class="source">This is a sample paragraph.</p>
    <p class="result">Encoded result: </p>

    const sourcePara = document.querySelector('.source');
    const resultPara = document.querySelector('.result');
    const string = sourcePara.textContent;

    const textEncoder = new TextEncoder();

    let encoded = textEncoder.encode(string);
    resultPara.textContent += encoded;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/#dom-textencoder-encode">Encoding<br />
<span class="small">The definition of 'TextEncoder.prototype.encode()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   The [`TextEncoder`](../textencoder) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextEncoder/encode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextEncoder/encode</a>
