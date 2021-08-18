# HTMLCanvasElement.toBlob()

The `HTMLCanvasElement.toBlob()` method creates a [`Blob`](../blob) object representing the image contained in the canvas; this file may be cached on the disk or stored in memory at the discretion of the user agent. If `type` is not specified, the image type is `image/png`. The created image is in a resolution of 96dpi.

The third argument is used when creating images using lossy compression (such as `image/jpeg`) to specify the quality of the output.

## Syntax

    canvas.toBlob(callback, mimeType, qualityArgument);

### Parameters

`callback`  
A callback function with the resulting [`Blob`](../blob) object as a single argument.

`mimeType` <span class="badge inline optional">Optional</span>  
A [`DOMString`](../domstring) indicating the image format. The default type is `image/png`.

`qualityArgument` <span class="badge inline optional">Optional</span>  
A [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) between `0` and `1` indicating image quality if the requested type is `image/jpeg `or `image/webp`. If this argument is anything else, the default values 0.92 and 0.80 are used for image/jpeg and image/webp respectively. Other arguments are ignored.

### Return value

None.

### Exceptions

`SecurityError`  
The canvas's bitmap is not origin clean; at least some of its contents come from secure

## Examples

### Getting a file representing the canvas

Once you have drawn content into a canvas, you can convert it into a file of any supported image format. The code snippet below, for example, takes the image in the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element whose ID is "canvas", obtains a copy of it as a PNG image, then appends a new [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element to the document, whose source image is the one created using the canvas.

    var canvas = document.getElementById('canvas');

    canvas.toBlob(function(blob) {
      var newImg = document.createElement('img'),
          url = URL.createObjectURL(blob);

      newImg.onload = function() {
        // no longer need to read the blob so it's revoked
        URL.revokeObjectURL(url);
      };

      newImg.src = url;
      document.body.appendChild(newImg);
    });

Note that here we're creating a PNG image; if you add a second parameter to the `toBlob()` call, you can specify the image type. For example, to get the image in JPEG format:

     canvas.toBlob(function(blob){...}, 'image/jpeg', 0.95); // JPEG at 95% quality

### A way to convert a canvas to an ico (Mozilla only)

This uses `-moz-parse` to convert the canvas to ico. Windows XP doesn't support converting from PNG to ico, so it uses bmp instead. A download link is created by setting the download attribute. The value of the download attribute is the name it will use as the file name.

    var canvas = document.getElementById('canvas');
    var d = canvas.width;
    ctx = canvas.getContext('2d');
    ctx.beginPath();
    ctx.moveTo(d / 2, 0);
    ctx.lineTo(d, d);
    ctx.lineTo(0, d);
    ctx.closePath();
    ctx.fillStyle = 'yellow';
    ctx.fill();

    function blobCallback(iconName) {
      return function(b) {
        var a = document.createElement('a');
        a.textContent = 'Download';
        document.body.appendChild(a);
        a.style.display = 'block';
        a.download = iconName + '.ico';
        a.href = window.URL.createObjectURL(b);
      }
    }
    canvas.toBlob(blobCallback('passThisString'), 'image/vnd.microsoft.icon',
                  '-moz-parse-options:format=bmp;bpp=32');

### Save toBlob to disk with OS.File (chrome/add-on context only)

This technique saves it to the desktop and is only useful in Firefox chrome context or add-on code, as OS APIs are not present on web sites.

    var canvas = document.getElementById('canvas');
    var d = canvas.width;
    ctx = canvas.getContext('2d');
    ctx.beginPath();
    ctx.moveTo(d / 2, 0);
    ctx.lineTo(d, d);
    ctx.lineTo(0, d);
    ctx.closePath();
    ctx.fillStyle = 'yellow';
    ctx.fill();

    function blobCallback(iconName) {
      return function(b) {
        var r = new FileReader();
        r.onloadend = function () {
        // r.result contains the ArrayBuffer.
        Cu.import('resource://gre/modules/osfile.jsm');
        var writePath = OS.Path.join(OS.Constants.Path.desktopDir,
                                     iconName + '.ico');
        var promise = OS.File.writeAtomic(writePath, new Uint8Array(r.result),
                                          {tmpPath:writePath + '.tmp'});
        promise.then(
          function() {
            console.log('successfully wrote file');
          },
          function() {
            console.log('failure writing file')
          }
        );
      };
      r.readAsArrayBuffer(b);
      }
    }

    canvas.toBlob(blobCallback('passThisString'), 'image/vnd.microsoft.icon',
                  '-moz-parse-options:format=bmp;bpp=32');

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-canvas-toblob">HTML Living Standard<br />
<span class="small">The definition of 'HTMLCanvasElement.toBlob' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since the latest snapshot, <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/scripting-1.html#dom-canvas-toblob">HTML 5.1<br />
<span class="small">The definition of 'HTMLCanvasElement.toBlob' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/scripting-1.html#dom-canvas-toblob">HTML5<br />
<span class="small">The definition of 'HTMLCanvasElement.toBlob' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of the <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a> containing the initial definition.</td></tr></tbody></table>

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

`toBlob`

50

79

12-79

18

10

37

11

50

50

18

37

11

5.0

`Image_quality`

50

79

25

No

Yes

No

50

No

25

No

No

No

## See also

- The interface defining it, [`HTMLCanvasElement`](../htmlcanvaselement).
- [`Blob`](../blob)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/toBlob" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/toBlob</a>
