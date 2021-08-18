# -moz-image-rect

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `-moz-image-rect` value for [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`background-image`](background-image) lets you use a portion of a larger image as a background.

## Syntax

    -moz-image-rect(<uri>(), top, right, bottom, left);

### Values

[`<url>()`](<url()>)  
The URI of the image from which to take the sub-image.

`top`  
The top edge, specified as an [`<integer>`](integer) or [`<percentage>`](percentage), of the sub-image within the specified image.

`right`  
The right edge, specified as an [`<integer>`](integer) or [`<percentage>`](percentage), of the sub-image within the specified image.

`bottom`  
The bottom edge, specified as an [`<integer>`](integer) or [`<percentage>`](percentage), of the sub-image within the specified image.

`left`  
The left edge, specified as an [`<integer>`](integer) or [`<percentage>`](percentage), of the sub-image within the specified image.

## Description

This property allows you to, for example, use different parts of one larger image as backgrounds in different parts of your content.

This works very similarly to the [`-moz-image-region`](-moz-image-region) property, which is used with the [`list-style-image`](list-style-image) property to use parts of an image as the bullets in lists. However, this can be used for any CSS background.

The syntax for the rectangle is similar to the [`rect()`](shape#syntax) function generating a [`<<shape>()>`](shape) CSS type. All four values are relative to the upper left corner of the image.

## Examples

This example loads an image and uses it in four segments to draw the Firefox logo in four [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) blocks. Clicking on their container causes the four segments to rotate around by swapping the [`background-image`](background-image) property values among the four [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) blocks.

### CSS

The CSS defines one container style, then the styles for the four boxes that comprise the complete image.

The container looks like this:

    #container {
      width:267px;
      height:272px;
      top:100px;
      left:100px;
      position:absolute;
      font-size:16px;
      text-shadow:white 0px 0px 6px;
      text-align:center;
    }

Then the four boxes defining the segments of the image are defined. Let's look at them one at a time.

    #box1 {
      background-image: -moz-image-rect(url(https://mdn.mozillademos.org/files/12053/firefox.png), 0%, 50%, 50%, 0%);
      width:133px;
      height:136px;
      position:absolute;
    }

This is the top-left corner of the image. It defines a rectangle containing the top-left quarter of the image in the file `firefox.jpg`.

    #box2 {
      background-image: -moz-image-rect(url(https://mdn.mozillademos.org/files/12053/firefox.png), 0%, 100%, 50%, 50%);
      width:133px;
      height:136px;
      position:absolute;
    }

This defines the top-right corner of the image.

The other corners follow a similar pattern:

    #box3 {
      background-image: -moz-image-rect(url(https://mdn.mozillademos.org/files/12053/firefox.png), 50%, 50%, 100%, 0%);
      width:133px;
      height:136px;
      position:absolute;
    }
    #box4 {
      background-image: -moz-image-rect(url(https://mdn.mozillademos.org/files/12053/firefox.png), 50%, 100%, 100%, 50%);
      width:133px;
      height:136px;
      position:absolute;
    }

### HTML

The HTML is quite simple:

    <div id="container" onclick="rotate()">
      <div id="box1" style="left:0px;top:0px;">Top left</div>
      <div id="box2" style="left:133px;top:0px;">Top right</div>
      <div id="box3" style="left:0px;top:136px;">Bottom left</div>
      <div id="box4" style="left:133px;top:136px;">Bottom right</div>
    </div>

This places the four segments of our image in a two-by-two box grid. These four segments are all contained within a larger [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) block whose primary purpose is to receive click events and dispatch them to our JavaScript code.

### The JavaScript code

This code handles the click event when the container receives a mouse click.

    function rotate() {
      var prevStyle = window.getComputedStyle(document.getElementById("box4"), null).getPropertyValue("background-image");

      // Now that we've saved the last one, start rotating

      for (var i=1; i<=4; i++) {
        var curId = "box" + i;

        // Shift the background images

        var curStyle = window.getComputedStyle(document.getElementById(curId), null).getPropertyValue("background-image");
        document.getElementById(curId).style.backgroundImage = prevStyle;
        prevStyle = curStyle;
      }
    }

This uses [`window.getComputedStyle()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle) to fetch the style of each element, shifting it to the following element. Notice that before it begins doing so it saves a copy of the last box's style since it will be overwritten by the third element's style. By copying the values of the [`background-image`](background-image) property from one element to the next with each mouse click, we achieve the desired effect.

### What it looks like

## Specifications

Not part of any standard.

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

`-moz-image-rect`

No

No

4

No

No

No

See [WebKit bug 32177](https://webkit.org/b/32177)

No

No

4

No

No

See [WebKit bug 32177](https://webkit.org/b/32177)

No

## See also

- [Mozilla CSS extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions)
- [CSS Backgrounds and Borders module](css_backgrounds_and_borders)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-image-rect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-image-rect</a>
