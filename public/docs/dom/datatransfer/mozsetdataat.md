# DataTransfer.mozSetDataAt()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `DataTransfer.mozSetDataAt()` method is used to add data to a specific index in the drag event's [`data transfer`](../datatransfer) object.

A data transfer may store multiple items, each at a given zero-based index. `mozSetDataAt()` may only be called with an index argument less than [`mozItemCount`](mozitemcount) in which case an existing item is modified, or equal to [`mozItemCount`](mozitemcount) in which case a new item is added, and the [`mozItemCount`](mozitemcount) is incremented by one.

Data should be added in order of preference, with the most specific format added first and the least specific format added last. If data of the given format already exists, it is replaced in the same position as the old data.

The data should be either a [`string`](../domstring), a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) or number type (which will be converted into a string) or an <span class="page-not-created">`nsISupports`</span>.

**Note**

This method is Firefox-specific.

## Syntax

    void dataTransfer.mozSetDataAt([type], data, index);

### Arguments

_type_  
A [`string`](../domstring) representing the type of the drag data to add to the [`drag data object`](../datatransfer).

_data_  
A <span class="page-not-created">`nsIVariant`</span> representing the data to add to the [`drag data object`](../datatransfer).

_index_  
A `unsigned long` representing the index of the data to add.

### Return value

void

## Example

This example shows the use of the `mozSetDataAt()` method in a `dragstart` handler.

    function dragstart_handler(event)
    {
      var dt = event.dataTransfer;
      var idx = dt.mozItemCount;
      // Add two new items to the drag transfer
      if (idx >= 0) {
        dt.mozSetDataAt("text/uri-list","http://www.example.com/", idx);
        dt.mozSetDataAt("text/html", "Hello World", idx+1);
      }
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

`mozSetDataAt`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozSetDataAt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozSetDataAt</a>
