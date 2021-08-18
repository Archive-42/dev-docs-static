# BarcodeDetector.detect()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `detect()` method of the [`BarcodeDetector`](../barcodedetector) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which fulfills with an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of detected barcodes within an image.

## Syntax

    var detectedBarcode = BarcodeDetector.detect(ImageBitmapSource);

### Parameters

_image_  
Receives an `ImageBitmapSource` as a parameter. This can be an [element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img), a [`Blob`](../blob) of type image or an [`ImageData`](../imagedata) object.

### Return value

Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which fulfills with an array of `detectedBarcode` objects with the following properties:

- `boundingBox`: A [`DOMRectReadOnly`](../domrectreadonly), which returns the dimensions of a rectangle representing the extent of a detected barcode, aligned with the image.
- `cornerPoints`: The x and y co-ordinates of the four corner points of the detected barcode relative to the image, starting with the top left and working clockwise. This may not be square due to perspective distortions within the image.
- `format`: The detected barcode format. (For a full list of formats see the [`Barcode Detection API overview page`](../barcode_detection_api)).
- `rawValue`: A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) decoded from the barcode data.

### Exceptions

`TypeError`  
No parameter is specified or the `type` is not that of an `ImageBitmapSource`.

## Examples

This example uses the `detect()` method to detect the barcodes within the given image. These are iterated over and the barcode data is logged to the console.

    barcodeDetector.detect(imageEl)
      .then(barcodes => {
        barcodes.forEach(barcode => console.log(barcode.rawData));
      }
      .catch(err => {
        console.log(err);
      })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/shape-detection-api/#dom-barcodedetector-detect">Accelerated Shape Detection in Images<br />
<span class="small">The definition of 'BarcodeDetector.detect()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`detect`

83

83

No

No

Yes

No

83

83

No

Yes

No

13.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BarcodeDetector/detect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BarcodeDetector/detect</a>
