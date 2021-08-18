# DataTransfer.setDragImage()

When a drag occurs, a translucent image is generated from the drag target (the element the `dragstart` event is fired at), and follows the mouse pointer during the drag. This image is created automatically, so you do not need to create it yourself. However, if a custom image is desired, the `DataTransfer.setDragImage()` method can be used to set the custom image to be used. The image will typically be an [`<image>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/image) element but it can also be a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) or any other visible element.

The method's `x` and `y` coordinates define how the image should appear relative to the mouse pointer. These coordinates define the offset into the image where the mouse cursor should be. For instance, to display the image so that the pointer is at its center, use values that are half the width and height of the image.

This method must be called in the `dragstart` event handler.

## Syntax

    void dataTransfer.setDragImage(img | element, xOffset, yOffset);

### Arguments

_img |_ element  
An image [`Element`](../element) element to use for the drag feedback image.

If [`Element`](../element) is an img element, then set the drag data store bitmap to the element's image (at its intrinsic size); otherwise, set the drag data store bitmap to an image generated from the given element (the exact mechanism for doing so is not currently specified).

_xOffset_  
A `long` indicating the horizontal offset within the image.

_yOffset_  
A `long` indicating the vertical offset within the image.

### Return value

void

## Example

This example shows how to use the `setDragImage()` method. Note the example refers to an image file named `example.gif`. If that file is present, it will be used as the drag image and if that file is not present, the browser will use its default drag image.

[demo](https://codepen.io/webgeeker/full/KBzrxE/)

    <!DOCTYPE html>
    <html lang=en>
    <title>Example of DataTransfer.setDragImage()</title>
    <meta name="viewport" content="width=device-width">
    <style>
      div {
        margin: 0em;
        padding: 2em;
      }
      #source {
        color: blue;
        border: 1px solid black;
      }
      #target {
        border: 1px solid black;
      }
    </style>
    <script>
    function dragstart_handler(ev) {
     console.log("dragStart");
     // Set the drag's format and data. Use the event target's id for the data
     ev.dataTransfer.setData("text/plain", ev.target.id);
     // Create an image and use it for the drag image
     // NOTE: change "example.gif" to an existing image or the image will not
     // be created and the default drag image will be used.
     var img = new Image();
     img.src = 'example.gif';
     ev.dataTransfer.setDragImage(img, 10, 10);
    }

    function dragover_handler(ev) {
     console.log("dragOver");
     ev.preventDefault();
    }

    function drop_handler(ev) {
     console.log("Drop");
     ev.preventDefault();
     // Get the data, which is the id of the drop target
     var data = ev.dataTransfer.getData("text");
     ev.target.appendChild(document.getElementById(data));
    }
    </script>
    <body>
    <h1>Example of <code>DataTransfer.setDragImage()</code></h1>
     <div>
       <p id="source" ondragstart="dragstart_handler(event);" draggable="true">
         Select this element, drag it to the Drop Zone and then release the selection to move the element.</p>
     </div>
     <div id="target" ondrop="drop_handler(event);" ondragover="dragover_handler(event);">Drop Zone</div>
    </body>
    </html>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-datatransfer-setdragimage">HTML Living Standard<br />
<span class="small">The definition of 'setDragImage()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#dom-datatransfer-setdragimage">HTML 5.1<br />
<span class="small">The definition of 'setDragImage()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Not included in W3C HTML5 <span class="spec-rec">Recommendation</span></td></tr></tbody></table>

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

`setDragImage`

Yes

18

3.5

?

Yes

Yes

Yes

Yes

4

Yes

No

Yes

## See also

- [Drag and drop](../html_drag_and_drop_api)
- [Drag Operations](../html_drag_and_drop_api/drag_operations)
- [Recommended Drag Types](../html_drag_and_drop_api/recommended_drag_types)
- [Dragging and Dropping Multiple Items](../html_drag_and_drop_api/multiple_items)
- [DataTransfer test - Paste or Drag](https://codepen.io/tech_query/pen/MqGgap)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/setDragImage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/setDragImage</a>
