# BarcodeDetector()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `BarcodeDetector()` constructor creates a new [`BarcodeDetector`](../barcodedetector) object which detects linear and two-dimensional barcodes in images.

## Syntax

    var BarcodeDetector = new BarcodeDetector();

### Parameters

_barcodeDetectorOptions_ <span class="badge inline optional">Optional</span>  
An options object containing a series of `BarcodeFormats` to search for in the subsequent [`detect()`](detect) calls. The options are:

- `formats`: An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of barcode formats as strings. To see a full list of supported formats see the <span class="page-not-created">`Barcode Detection API overview page`</span>.

## Examples

This example creates a new barcode detector object, with specified supported formats and tests for browser compatibility.

    // create new detector
    var barcodeDetector = new BarcodeDetector({formats: ['code_39', 'codabar', 'ean_13']});

    // check compatibility
    if (barcodeDetector) {
      console.log('Barcode Detector supported!');
    } else {
      console.log('Barcode Detector is not supported by this browser.');
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/shape-detection-api/#dom-barcodedetector-barcodedetector">Accelerated Shape Detection in Images<br />
<span class="small">The definition of 'BarcodeDetector.BarcodeDetector()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BarcodeDetector/BarcodeDetector" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BarcodeDetector/BarcodeDetector</a>
