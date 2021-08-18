HTMLCanvasElement.mozGetAsFile()
================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The non-standard, Firefox-specific the [`HTMLCanvasElement`](../htmlcanvaselement) method [`mozGetAsFile()`](mozgetasfile) returns a memory-based [`File`](../file) object representing the image contained in the canvas.

Syntax
------

    canvas.mozGetAsFile(name, type);

### Parameters

`name`  
A [`DOMString`](../domstring) indicating the file name to give the file representing the image file in memory.

 `type` <span class="badge inline optional">Optional</span>   
A [`DOMString`](../domstring) which specifies the image file format to use when creating the new image file. The default type is `image/png`. For other options, see our [Image file type and format guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types).

### Return value

A [`File`](../file) object representing the image contained in the canvas. The file's data is entirely located in memory until such time as it is explicitly written to disk.

Examples
--------

This example creates an image file from the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element on the page, then uses a [`FileReader`](../filereader) to read the image data from the file.

### HTML

    <canvas id="canvas" width="100" height="100"></canvas>
    <p><a href="#" id="link">Click here to try out mozGetAsFile()</a>.</p>

### JavaScript

The following code uses `mozGetAsFile()` to create a [`File`](../file) object from the canvas and appends it as an image to the page by loading it as a data URL using the [`readAsDataURL()`](../filereader/readasdataurl) method. Then a new [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element is created using the new data URL.

    function draw() {
      var canvas = document.getElementById('canvas');
      var ctx = canvas.getContext('2d');

      ctx.fillStyle = 'rgb(200, 0, 0)';
      ctx.fillRect(10, 10, 55, 50);

      ctx.fillStyle = 'rgba(0, 0, 200, 0.5)';
      ctx.fillRect(30, 30, 55, 50);

      var link = document.getElementById('link');
      link.addEventListener('click', copy);
    }

    function copy() {
      var canvas = document.getElementById('canvas');
      var f = canvas.mozGetAsFile('test.png');
      var reader = new FileReader();
      reader.readAsDataURL(f);

      reader.onloadend = function() {
       var newImg = document.createElement('img');
       newImg.src = reader.result;
       document.body.appendChild(newImg);
      }
    }

    window.addEventListener('load', draw);

Specifications
--------------

Not part of any specification.

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

`mozGetAsFile`

No

No

4-74

`mozGetAsFile()` was deprecated in Firefox 26 (in 2013) and was removed entirely in Firefox 74.

No

No

No

No

No

4

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/mozGetAsFile" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/mozGetAsFile</a>
