# Document.releaseCapture()

The `releaseCapture()` method releases mouse capture if it's currently enabled on an element within this document. Enabling mouse capture on an element is done by calling [`element.setCapture()`](../element/setcapture).

## Syntax

    document.releaseCapture();

Once mouse capture is released, mouse events will no longer all be directed to the element on which capture is enabled.

## Example

See the [example](../element/setcapture#example) for [`element.setCapture()`](../element/setcapture).

## Specifications

Based on Internet Explorer's implementation.

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

`releaseCapture`

No

No

4

5

No

No

No

No

4

No

No

No

## See also

- [`element.setCapture()`](../element/setcapture)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/releaseCapture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/releaseCapture</a>
