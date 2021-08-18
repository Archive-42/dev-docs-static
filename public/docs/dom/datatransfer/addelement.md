# DataTransfer.addElement()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `DataTransfer.addElement()` method sets the drag source to the given element. This element will be the element to which `drag` and `dragend` events are fired, and not the default target (the node that was dragged).

**Note**

This method is Firefox-specific.

## Syntax

    void dataTransfer.addElement(el);

### Arguments

_el_  
The [`Element`](../element) to set as the drag source.

### Return value

void

## Example

This example shows the use of the `addElement()` method

    function change_drag_node(event, node)
    {
      var dt = event.dataTransfer;
      dt.addElement(node);
    }

## Specifications

This method is not defined in any Web standard.

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

`addElement`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/addElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/addElement</a>
