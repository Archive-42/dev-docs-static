ImageCapture.grabFrame()
========================

The `grabFrame()` method of the [`ImageCapture`](../imagecapture) interface takes a snapshot of the live video in a [`MediaStreamTrack`](../mediastreamtrack) and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`ImageBitmap`](../imagebitmap) containing the snapshot.

Syntax
------

    const bitmapPromise = imageCapture.grabFrame()

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an [`ImageBitmap`](../imagebitmap) object.

Example
-------

This example is extracted from this [Simple Image Capture demo](https://simpl.info/imagecapture/). It shows how to use the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by `grabFrame()` to copy the returned frame to a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element. For simplicity it does not show how to instantiate the [`ImageCapture`](../imagecapture) object.

    var grabFrameButton = document.querySelector('button#grabFrame');
    var canvas = document.querySelector('canvas');

    grabFrameButton.onclick = grabFrame;

    function grabFrame() {
      imageCapture.grabFrame()
      .then(function(imageBitmap) {
        console.log('Grabbed frame:', imageBitmap);
        canvas.width = imageBitmap.width;
        canvas.height = imageBitmap.height;
        canvas.getContext('2d').drawImage(imageBitmap, 0, 0);
        canvas.classList.remove('hidden');
      })
      .catch(function(error) {
        console.log('grabFrame() error: ', error);
      });
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-image/#dom-imagecapture-grabframe">MediaStream Image Capture<br />
<span class="small">The definition of 'grabFrame()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`grabFrame`

59

≤79

No

See [bug 888177](https://bugzil.la/888177).

No

46

No

59

59

No

See [bug 888177](https://bugzil.la/888177).

43

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageCapture/grabFrame" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ImageCapture/grabFrame</a>
