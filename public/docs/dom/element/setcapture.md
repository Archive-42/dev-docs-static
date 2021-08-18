# Element.setCapture()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Call this method during the handling of a mousedown event to retarget all mouse events to this element until the mouse button is released or [`document.releaseCapture()`](../document/releasecapture) is called.

**Warning**

This interface never had much cross-browser support and you probably looking for [`element.setPointerCapture`](setpointercapture) instead, from the Pointer Events API.

## Syntax

    element.setCapture(retargetToElement);

`retargetToElement`  
If `true`, all events are targeted directly to this element; if `false`, events can also fire at descendants of this element.

## Example

In this example, the current mouse coordinates are drawn while you mouse around after clicking and holding down on an element.

    <html>
    <head>
      <title>Mouse Capture Example</title>
      <style type="text/css">
        #myButton {
          border: solid black 1px;
          color: black;
          padding: 2px;
          box-shadow: black 2px 2px;
        }
      </style>

      <script type="text/javascript">
        function init() {
          var btn = document.getElementById("myButton");
          if (btn.setCapture) {
            btn.addEventListener("mousedown", mouseDown, false);
            btn.addEventListener("mouseup", mouseUp, false);
          } else {
            document.getElementById("output").textContent
              = "Sorry, there appears to be no setCapture support on this browser";
          }
        }

        function mouseDown(e) {
          e.target.setCapture();
          e.target.addEventListener("mousemove", mouseMoved, false);
        }

        function mouseUp(e) {
          e.target.removeEventListener("mousemove", mouseMoved, false);
        }

        function mouseMoved(e) {
          var output = document.getElementById("output");
          output.textContent = `Position: ${e.clientX}, ${e.clientY}`;
        }
      </script>
    </head>
    <body onload="init()">
      <p>This is an example of how to use mouse capture on elements in Gecko 2.0.</p>
      <p><a id="myButton" href="#">Test Me</a></p>
      <div id="output">No events yet</div>
    </body>
    </html>

[View Live Examples](https://media.prod.mdn.mozit.cloud/samples/domref/mousecapture.html)

## Notes

The element may not be scrolled completely to the top or bottom, depending on the layout of other elements.

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

`setCapture`

No

12-79

4

5

The `retargetToElement` parameter to `Element.setCapture()` was introduced in Internet Explorer 5.5.

No

No

No

No

4

No

No

No

## See also

- [`document.releaseCapture()`](../document/releasecapture)
- [`element.setPointerCapture`](setpointercapture)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/setCapture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/setCapture</a>
