# Document.mozSetImageElement()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Document.mozSetImageElement()` method changes the element being used as the CSS background for a background with a given background element ID.

## Syntax

    document.mozSetImageElement(imageElementId, imageElement);

### Parameters

- `imageElementId` is a string indicating the name of an element that has been specified as a background image using the [`-moz-element()`](<https://developer.mozilla.org/en-US/docs/Web/CSS/element()>) CSS function.
- `imageElement` is the new element to use as the background corresponding to that image element string. Specify `null` to remove the background element.

## Example

This example changes the background of a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) block each time the block is clicked by the user.

[View this example live](https://media.prod.mdn.mozit.cloud/samples/domref/mozSetImageElement.html).

    <style type="text/css">
      #mybox {
        background-image: -moz-element(#canvasbg);
        text-align: center;
        width: 400px;
        height: 400px;
        cursor: pointer;
      }
    </style>

The CSS defined by the [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) block above is used by our [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) to use an element with the id "canvasbg" as its background.

    var c = 0x00;
    function clicked() {
      var canvas = document.createElement("canvas");
      canvas.setAttribute("width", 100);
      canvas.setAttribute("height", 100);

      var ctx = canvas.getContext('2d');
      ctx.fillStyle = "#" + c.toString(16) + "0000";
      ctx.fillRect(25, 25, 75, 75);

      c += 0x11;
      if (c > 0xff) {
        c = 0x00;
      }

      document.mozSetImageElement("canvasbg", canvas);
    }

The code here is called each time the user clicks the [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element. It creates a new [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) with the width and height set to 100 pixels, then draws into it a 50 by 50 pixel square. Each time the function is called, the square is a different color (its red component is increased each time), so each time the user clicks the element, the background is filled with a brighter and brighter pattern of red tiles.

Once the canvas is drawn, `document.mozSetImageElement()` is called to set the background for any CSS using the ID "canvasbg" as its background element ID to be our new canvas.

## Specifications

Not part of any specification.

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

`mozSetImageElement`

No

No

4

No

No

No

No

No

4

No

No

No

## See also

- [`-moz-element()`](<https://developer.mozilla.org/en-US/docs/Web/CSS/element()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/mozSetImageElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/mozSetImageElement</a>
