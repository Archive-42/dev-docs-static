# DataTransfer.mozItemCount

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `DataTransfer.mozItemCount` property returns the number of items being dragged. This can be used, for example, to get the number of files being dragged.

**Note:** This property is Gecko-specific.

This property is <span class="badge inline readonly">Read only </span>.

## Syntax

    dataTransfer.mozItemCount;

### Return value

A `number` representing the number of items being dragged.

## Example

This example shows the use of the `mozItemCount` property.

    function drop_handler(event)
    {
      var files = [];
      var dt = event.dataTransfer;
      for (var i = 0; i < dt.mozItemCount; i++)
        files.push(dt.mozGetDataAt("application/x-moz-file", i));
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

`mozItemCount`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozItemCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/mozItemCount</a>
