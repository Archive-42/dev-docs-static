ReadableStream.pipeTo()
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `pipeTo()` method of the [`ReadableStream`](../readablestream) interface pipes the current `ReadableStream` to a given [`WritableStream`](../writablestream) and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills when the piping process completes successfully, or rejects if any errors were encountered.

Piping a stream will generally lock it for the duration of the pipe, preventing other readers from locking it.

Syntax
------

    var promise = readableStream.pipeTo(destination[, options]);

### Parameters

destination  
A [`WritableStream`](../writablestream) that acts as the final destination for the [`ReadableStream`](../readablestream).

options <span class="badge inline optional">Optional</span>   
The options that should be used when piping to the `writable` stream. Available options are:

1.  `preventClose`: If this is set to `true`, the source `ReadableStream` closing will no longer cause the destination `WritableStream` to be closed. The method will return a fulfilled promise once this process completes, unless an error is encountered while closing the destination in which case it will be rejected with that error.
2.  `preventAbort`: If this is set to `true`, errors in the source `ReadableStream` will no longer abort the destination `WritableStream`. The method will return a promise rejected with the source’s error, or with any error that occurs during aborting the destination.
3.  `preventCancel`: If this is set to `true`, errors in the destination `WritableStream` will no longer cancel the source `ReadableStream`. In this case the method will return a promise rejected with the source’s error, or with any error that occurs during canceling the source. In addition, if the destination writable stream starts out closed or closing, the source readable stream will no longer be canceled. In this case the method will return a promise rejected with an error indicating piping to a closed stream failed, or with any error that occurs during canceling the source.
4.  `signal`: If set to an `AbortSignal` object, ongoing pipe operations can then be aborted via the corresponding `AbortController`.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the piping process has completed.

### Exceptions

TypeError  
The `writableStream` and/or `readableStream` objects are not a writable stream/readable stream, or one or both of the streams are locked.

Examples
--------

    // Fetch the original image
    fetch('png-logo.png')
    // Retrieve its body as ReadableStream
    .then(response => response.body)
    .then(body => body.pipeThrough(new PNGTransformStream()))
    .then(rs => rs.pipeTo(new FinalDestinationStream()))

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rs-pipe-to">Streams<br />
<span class="small">The definition of 'pipeTo()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`pipeTo`

59

79

No

No

46

10.1

59

59

No

43

10.3

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream/pipeTo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream/pipeTo</a>
