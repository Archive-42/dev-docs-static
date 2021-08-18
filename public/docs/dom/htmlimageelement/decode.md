HTMLImageElement.decode()
=========================

The `decode()` method of the [`HTMLImageElement`](../htmlimageelement) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the image is decoded and it is safe to append the image to the DOM. This can be used to initiate loading of the image prior to attaching it to an element in the DOM (or adding it to the DOM as a new element), so that the image can be rendered immediately upon being added to the DOM. This, in turn, prevents the rendering of the next frame after adding the image to the DOM from causing a delay while the image loads.

Syntax
------

    var promise = HTMLImageElement.decode();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is resolved once the image data is ready to be used.

### Exceptions

`EncodingError`  
A [`DOMException`](../domexception) indicating that an error occurred while decoding the image.

Usage notes
-----------

One potential use case for `decode()`: when loading very large images (for example, in an online photo album), you can present a low resolution thumbnail image initially and then replace that image with the full-resolution image by instantiating a new [`HTMLImageElement`](../htmlimageelement), setting its source to the full-resolution image's URL, then using `decode()` to get a promise which is resolved once the full-resolution image is ready for use. At that time, you can then replace the low-resolution image with the full-resolution one that's now available.

Examples
--------

The following example shows how to use the `decode()` method to control when an image is appended to the DOM. Without a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)-returning method, you would add the image to the DOM in a `load` event handler, such as by using the [`img.onload`](../globaleventhandlers/onload) event handler, and by handling the error in the `error` event's handler.

    const img = new Image();
    img.src = 'nebula.jpg';
    img.decode()
    .then(() => {
      document.body.appendChild(img);
    })
    .catch((encodingError) => {
      // Do something with the error.
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-img-decode">HTML Living Standard<br />
<span class="small">The definition of 'decode()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`decode`

64

79

68

No

51

11.1

64

64

68

47

11.3

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/decode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/decode</a>
