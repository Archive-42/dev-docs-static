# DataTransfer.mozClearDataAt()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `DataTransfer.mozClearDataAt()` method removes the data associated with the given format for an item at the specified index. The index must be in the range from zero to the number of items minus one.

If the `format` argument is not provided, then the data associated with all formats is removed. If the format is not found, then this method has no effect. If the last format for the item is removed, the entire item is removed, reducing [`mozItemCount`](mozitemcount) by one.

Removing the last format for a particular index removes that item entirely, shifting the remaining items down and changing their indices.

**Note:** This method is Gecko-specific.

## Syntax

    void dataTransfer.mozClearDataAt([type], index);

### Arguments

_type_  
A [`string`](../domstring) representing the type of the drag data to remove from the [`drag data object`](../datatransfer).

_index_  
A `unsigned long` representing the index of the data to remove.

### Return value

void

## Example

This example shows the use of the `mozClearDataAt()` method in a `dragend` event handler.

    function dragend_handler(event)
    {
      var dt = event.dataTransfer;
      // Remove a text/html item
      dt.mozClearDataAt("text/html", 1);
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

`mozClearDataAt`

No

No

3.5-71

No

No

No

No

No

4-79

No

No

No

## See also

- [Drag and drop](../html_drag_and_drop_api)
- [Drag Operations](../html_drag_and_drop_api/drag_operations)
- [Recommended Drag Types](../html_drag_and_drop_api/recommended_drag_types)
- [Dragging and Dropping Multiple Items](../html_drag_and_drop_api/multiple_items)
- [DataTransfer test - Paste or Drag](https://codepen.io/tech_query/pen/MqGgap)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozClearDataAt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozClearDataAt</a>
