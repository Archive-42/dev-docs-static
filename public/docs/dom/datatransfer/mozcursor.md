# DataTransfer.mozCursor

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `DataTransfer.mozCursor` property returns or sets the drag cursor's state. This is primarily used to control the cursor during tab drags.

The possible values are:

auto  
Uses the default system behavior.

default  
Uses the default Gecko behavior, which is to set the cursor to an arrow during the drag operation.

**Note:** If any value other than `default` is set, `auto` is assumed.

**Note:** This property is currently only implemented on Windows.

**Note:** This property is Gecko-specific.

## Syntax

    dataTransfer.mozCursor;

### Return value

A [`DOMString`](../domstring) representing one of the values listed above.

## Example

This example shows the use of the `mozCursor` property.

    function drop_handler(event)
    {
      var dragData = event.dataTransfer;
      console.log("mozCursor = " + dragData.mozCursor);
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

`mozCursor`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozCursor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozCursor</a>
