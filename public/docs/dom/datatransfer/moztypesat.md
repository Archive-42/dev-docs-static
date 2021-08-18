# DataTransfer.mozTypesAt()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `DataTransfer.mozTypesAt()` method returns a list of the format types that are stored for an item at the specified index. If the index is not in the range from 0 to the number of items minus one, an empty string list is returned.

**Note**

This method is Firefox-specific.

## Syntax

    mozTypesAt(index);

### Arguments

_index_  
A `unsigned long` that is the index of the data for which to retrieve the types.

### Return value

<span class="page-not-created">`nsIVariant`</span>  
A list of data formats (which are [`strings`](../domstring)). If the index is not in the range from 0 to the number of items minus one, an empty string list is returned.

## Example

This example shows the use of the `mozTypesAt()` method in a `drop` event handler.

    function drop_handler(event)
    {
      var dt = event.dataTransfer;
      var count = dt.mozItemCount;
      output("Items: " + count + "\n");

      for (var i = 0; i < count; i++) {
        output(" Item " + i + ":\n");
        var types = dt.mozTypesAt(i);
        for (var t = 0; t < types.length; t++) {
          output("  " + types[t] + ": ");
          try {
            var data = dt.mozGetDataAt(types[t], i);
            output("(" + (typeof data) + ") : <" + data + " >\n");
          } catch (ex) {
            output("<>\n");
            dump(ex);
          }
        }
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

`mozTypesAt`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozTypesAt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozTypesAt</a>
