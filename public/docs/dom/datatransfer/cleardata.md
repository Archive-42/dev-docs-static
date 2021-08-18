# DataTransfer.clearData()

The `DataTransfer.clearData()` method removes the drag operation's [`drag data`](../datatransfer) for the given type. If data for the given type does not exist, this method does nothing.

If this method is called with no arguments or the format is an empty [`string`](../domstring), the data of all types will be removed.

This method does _not_ remove files from the drag operation, so it's possible for there still to be an entry with the type `"Files"` left in the object's [`DataTransfer.types`](types) list if there are any files included in the drag.

This method can only be used in the handler for the `dragstart` event, because that's the only time the drag operation's data store is writeable.

## Syntax

    DataTransfer.clearData([format]);

### Parameters

`format` <span class="badge inline optional">Optional</span>  
A [`string`](../domstring) which specifies the type of data to remove. If this parameter is an empty string or is not provided, the data for all types is removed.

## Example

This example shows the use of the [`DataTransfer`](../datatransfer) object's [`getData()`](getdata), [`setData()`](setdata) and [`clearData()`](cleardata) methods.

### HTML

    <span class="tweaked" id="source" draggable="true">
      Select this element, drag it to the Drop Zone and then release the selection to move the element.
    </span>
    <span class="tweaked" id="target">Drop Zone</span>
    <div>Status: <span id="status">Drag to start</span></div>
    <div>Data is: <span id="data">uninitialized</span></div>

### CSS

    span.tweaked {
      display: inline-block;
      margin: 1em 0;
      padding: 1em 2em;
    }

    #source {
      color: blue;
      border: 1px solid black;
    }

    #target {
      border: 1px solid black;
    }

### JavaScript

    window.addEventListener('DOMContentLoaded', function () {
      // Select HTML elements
      var draggable = document.getElementById('source');
      var dropable = document.getElementById('target');
      var status = document.getElementById('status');
      var data = document.getElementById('data');
      var dropped = false;

      // Register event handlers
      draggable.addEventListener('dragstart', dragStartHandler);
      draggable.addEventListener('dragend', dragEndHandler);
      dropable.addEventListener('dragover', dragOverHandler);
      dropable.addEventListener('dragleave', dragLeaveHandler);
      dropable.addEventListener('drop', dropHandler);

      function dragStartHandler (event) {
        status.textContent = 'Drag in process';

        // Change target element's border to signify drag has started
        event.currentTarget.style.border = '1px dashed blue';

        // Start by clearing existing clipboards; this will affect all types since we
        // don't give a specific type.

        event.dataTransfer.clearData();

        // Set the drag's format and data (use event target's id for data)
        event.dataTransfer.setData('text/plain', event.target.id);

        data.textContent = event.dataTransfer.getData('text/plain');
      }

      function dragEndHandler (event) {
        if (!dropped) {
          status.textContent = 'Drag canceled';
        }

        data.textContent = event.dataTransfer.getData('text/plain') || 'empty';

        // Change border to signify drag is no longer in process
        event.currentTarget.style.border = '1px solid black';

        if (dropped) {
          // Remove all event listeners
          draggable.removeEventListener('dragstart', dragStartHandler);
          draggable.removeEventListener('dragend', dragEndHandler);
          dropable.removeEventListener('dragover', dragOverHandler);
          dropable.removeEventListener('dragleave', dragLeaveHandler);
          dropable.removeEventListener('drop', dropHandler);
        }
      }

      function dragOverHandler (event) {
        status.textContent = 'Drop available';

        event.preventDefault();
      }

      function dragLeaveHandler (event) {
        status.textContent = 'Drag in process (drop was available)';

        event.preventDefault();
      }

      function dropHandler (event) {
        dropped = true;

        status.textContent = 'Drop done';

        event.preventDefault();

        // Get data linked to event format « text »
        var _data = event.dataTransfer.getData('text/plain');
        var element = document.getElementById(_data);

        // Append drag source element to event's target element
        event.target.appendChild(element);

        // Change CSS styles and displayed text
        element.style.cssText = 'border: 1px solid black;display: block; color: red';
        element.textContent = "I'm in the Drop Zone!";
      }
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-datatransfer-cleardata">HTML Living Standard<br />
<span class="small">The definition of 'DataTransfer.clearData()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#dom-datatransfer-cleardata">HTML 5.1<br />
<span class="small">The definition of 'DataTransfer.clearData()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`clearData`

Yes

12

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/clearData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/clearData</a>
