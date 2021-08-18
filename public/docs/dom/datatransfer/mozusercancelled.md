# DataTransfer.mozUserCancelled

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `DataTransfer.mozUserCancelled` property is used in the `dragend` event handler to determine if the user canceled the drag or not. If the user canceled the event, the property returns `true` and returns `false` otherwise. This property only applies to the `dragend` event.

**Note**&gt;

This property is Firefox-specific.

This property is <span class="badge inline readonly">Read only </span>.

## Syntax

    dataTransfer.mozUserCancelled;

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) representing `true` if the user canceled the drag event and returns `false` otherwise.

## Example

This example shows the use of the `mozUserCancelled` property in the `dragend` event handler.

    function dragend_handler(event)
    {
      var dragData = event.dataTransfer;
      console.log("mozUserCancelled = " + dragData.mozUserCancelled);
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

`mozUserCancelled`

No

No

3.5

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozUserCancelled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozUserCancelled</a>
