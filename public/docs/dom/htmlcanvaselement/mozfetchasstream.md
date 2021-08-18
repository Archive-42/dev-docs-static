# HTMLCanvasElement.mozFetchAsStream()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `HTMLCanvasElement.mozFetchAsStream()` internal method used to create a new input stream that, when ready, would provide the contents of the canvas as image data. However, this non-standard and internal method has been removed.

## Syntax

    void canvas.mozFetchAsStream(callback, type);

### Parameters

`callback`  
An <span class="page-not-created">`nsIInputStreamCallback`</span>.

`type` <span class="badge inline optional">Optional</span>  
A [`DOMString`](../domstring) indicating the image format. The default type is `image/png`.

### Return value

None.

## Examples

### Save to disk with `mozFetchAsStream` (Chrome context only)

This technique also converts it to ico, however it will not work in Windows XP as WinXP cannot convert from PNG to ICO. It saves to the desktop it uses FileUtils.jsm. Also uses NetUtil.jsm

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

    var netutilCallback = function() {
        return function(result) {
           if (!Components.isSuccessCode(result)) {
              alert('FAILED to create icon');
           } else {
               alert('successfully made');
           }
        };
    }

    var mfasCallback = function(iconName) {
        return function(inStream) {
           var file = FileUtils.getFile('Desk', [iconName + '.ico']);
           var outStream = FileUtils.openFileOutputStream(file);
           Cu.import('resource://gre/modules/NetUtil.jsm');
           NetUtil.asyncCopy(inStream, outStream, netutilCallback());
        }
    }

    canvas.mozFetchAsStream(mfasCallback('myIcon'), 'image/vnd.microsoft.icon');

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

`mozFetchAsStream`

No

No

13-23

No

No

No

No

No

14-23

No

No

No

## See also

- The interface defining it, [`HTMLCanvasElement`](../htmlcanvaselement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/mozFetchAsStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/mozFetchAsStream</a>
