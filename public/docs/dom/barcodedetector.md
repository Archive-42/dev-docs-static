# BarcodeDetector

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `BarcodeDetector` interface of the [`Barcode Detection API`](barcode_detection_api) allows detection of linear and two dimensional barcodes in images.

## Constructors

[`BarcodeDetector.BarcodeDetector()`](barcodedetector/barcodedetector)  
Creates and returns a `BarcodeDetector` object, with optional `barcodeDetectorOptions`

## Methods

[`detect()`](barcodedetector/detect)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which fulfills with an array of `detectedBarcode` objects with the following properties:

- `boundingBox`: A [`DOMRectReadOnly`](domrectreadonly), which returns the dimensions of a rectangle representing the extent of a detected barcode, aligned with the image.
- `cornerPoints`: The x and y co-ordinates of the four corner points of the detected barcode relative to the image, starting with the top left and working clockwise. This may not be square due to perspective distortions within the image.
- `format`: The detected barcode format. (For a full list of formats see the \[landing page\])
- `rawValue`: A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) decoded from the barcode data.

[`getSupportedFormats()`](barcodedetector/getsupportedformats)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which fulfills with an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of supported [barcode format types](barcode_detection_api#supported_barcode_formats).

## Examples

### Creating A Detector

This example creates a new barcode detector object, with specified supported formats and tests for browser compatibility.

    // create new detector
    var barcodeDetector = new BarcodeDetector({formats: ['code_39', 'codabar', 'ean_13']});

    // check compatibility
    if (barcodeDetector) {
      console.log('Barcode Detector supported!');
    } else {
      console.log('Barcode Detector is not supported by this browser.');
    }

### Getting Supported Formats

The following example calls the `getSupportFormat()` static method and logs the results to the console.

    // check supported types
    BarcodeDetector.getSupportedFormats()
      .then(formats => {
        supportedFormats.forEach(format => console.log(format));
      });

### Detect Barcodes

This example uses the `detect()` method to detect the barcodes within the given image. These are iterated over and the barcode data is logged to the console.

      barcodeDetector.detect(imageEl)
        .then(barcodes => {
          barcodes.forEach(barcode => console.log(barcode.rawData));
        })
        .catch(err => {
          console.log(err);
        })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/shape-detection-api/#barcodedetector">Accelerated Shape Detection in Images<br />
<span class="small">The definition of 'BarcodeDetector' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BarcodeDetector`

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

`BarcodeDetector`

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

`getSupportedFormats`

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

## See also

- [barcodefaq.com: A website with information about different barcodes and examples of the different types.](https://www.barcodefaq.com/)
- [Accelerated Shape Detection in Images](https://web.dev/shape-detection/#barcodedetector)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BarcodeDetector" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BarcodeDetector</a>
