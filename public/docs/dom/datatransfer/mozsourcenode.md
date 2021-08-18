# DataTransfer.mozSourceNode

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `DataTransfer.mozSourceNode` property is used to determine the [`Node`](../node) over which the mouse cursor was located when the drag operation was initiated (for example, when a [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) was clicked). For external drags or if the calling function cannot reach the node, `null` is returned.

**Note**&gt;

This property is Firefox-specific.

This property is <span class="badge inline readonly">Read only </span>.

## Syntax

    dataTransfer.mozSourceNode;

### Return value

A [`Node`](../node) representing `node` where the drag originated. Returns `null` for external drags or if the node cannot be accessed.

## Example

This example shows the use of the `mozSourceNode` property in the `dragend` event handler.

    function dragend_handler(event)
    {
      var dragData = event.dataTransfer;
      var node = dragData.mozSourceNode;
      if (node != null)
        console.log("mozSourceNode = " + dragData.mozSourceNode);
      else
        console.log("mozSourceNode is null");
    }

## Specifications

This property is not defined in any Web standard.

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

`mozSourceNode`

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

- [Drag and drop](../html_drag_and_drop_api)
- [Drag Operations](../html_drag_and_drop_api/drag_operations)
- [Recommended Drag Types](../html_drag_and_drop_api/recommended_drag_types)
- [Dragging and Dropping Multiple Items](../html_drag_and_drop_api/multiple_items)
- [DataTransfer test - Paste or Drag](https://codepen.io/tech_query/pen/MqGgap)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozSourceNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozSourceNode</a>
