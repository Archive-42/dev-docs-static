# BarcodeDetector.getSupportedFormats()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `getSupportedFormats()` static method of the [`BarcodeDetector`](../barcodedetector) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which fulfills with an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of supported barcode format types.

## Syntax

    var supportedFormats = BarcodeDetector.getSupportedFormats();

### Parameters

This method receives no parameters.

### Return value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [supported barcode format types](../barcode_detection_api#supported_barcode_formats).

### Exceptions

No exceptions are thrown.

## Examples

The following example calls the `getSupportFormat()` static method and logs the results to the console.

    // check supported types
    BarcodeDetector.getSupportedFormats()
      .then(supportedFormats => {
        supportedFormats.forEach(format => console.log(format));
      });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/shape-detection-api/#dom-barcodedetector-getsupportedformats">Accelerated Shape Detection in Images<br />
<span class="small">The definition of 'BarcodeDetector.getSupportedFormats()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BarcodeDetector/getSupportedFormats" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BarcodeDetector/getSupportedFormats</a>
