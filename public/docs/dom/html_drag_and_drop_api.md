HTML Drag and Drop API
======================

**HTML Drag and Drop** interfaces enable applications to use drag-and-drop features in browsers. The user may select *draggable* elements with a mouse, drag those elements to a *droppable* element, and drop them by releasing the mouse button. A translucent representation of the *draggable* elements follows the pointer during the drag operation.

For web sites, extensions, and XUL applications, you can customize which elements can become *draggable*, the type of feedback the *draggable* elements produce, and the *droppable* elements.

This overview of HTML Drag and Drop includes a description of the interfaces, basic steps to add drag-and-drop support to an application, and an interoperability summary of the interfaces.

Drag Events
-----------

HTML drag-and-drop uses the [`DOM event model`](event) and *[`drag events`](dragevent)* inherited from [`mouse events`](mouseevent). A typical *drag operation* begins when a user selects a *draggable* element, drags the element to a *droppable* element, and then releases the dragged element.

During drag operations, several event types are fired, and some events might fire many times, such as the [`drag`](document/drag_event) and [`dragover`](document/dragover_event) events.

Each [drag event type](dragevent#event_types) has an associated [global event handler](dragevent#globaleventhandlers):

<table><thead><tr class="header"><th>Event</th><th>On Event Handler</th><th>Fires when…</th></tr></thead><tbody><tr class="odd"><td><a href="document/drag_event"><code>drag</code></a></td><td><a href="globaleventhandlers/ondrag"><code>ondrag</code></a></td><td>…a <em>dragged item</em> (element or text selection) is dragged.</td></tr><tr class="even"><td><a href="document/dragend_event"><code>dragend</code></a></td><td><a href="globaleventhandlers/ondragend"><code>ondragend</code></a></td><td>…a drag operation ends (such as releasing a mouse button or hitting the Esc key; see <a href="html_drag_and_drop_api/drag_operations#dragend">Finishing a Drag</a>.)</td></tr><tr class="odd"><td><a href="document/dragenter_event"><code>dragenter</code></a></td><td><a href="globaleventhandlers/ondragenter"><code>ondragenter</code></a></td><td>…a dragged item enters a valid drop target. (See <a href="html_drag_and_drop_api/drag_operations#droptargets">Specifying Drop Targets</a>.)</td></tr><tr class="even"><td><span class="page-not-created"><code>dragexit</code></span></td><td><a href="globaleventhandlers/ondragleave"><code>ondragexit</code></a></td><td>…an element is no longer the drag operation's immediate selection target.</td></tr><tr class="odd"><td><a href="document/dragleave_event"><code>dragleave</code></a></td><td><a href="globaleventhandlers/ondragleave"><code>ondragleave</code></a></td><td>…a dragged item leaves a valid drop target.</td></tr><tr class="even"><td><a href="document/dragover_event"><code>dragover</code></a></td><td><a href="globaleventhandlers/ondragover"><code>ondragover</code></a></td><td>…a dragged item is being dragged over a valid drop target, every few hundred milliseconds.</td></tr><tr class="odd"><td><a href="document/dragstart_event"><code>dragstart</code></a></td><td><a href="globaleventhandlers/ondragstart"><code>ondragstart</code></a></td><td>…the user starts dragging an item. (See <a href="html_drag_and_drop_api/drag_operations#dragstart">Starting a Drag Operation</a>.)</td></tr><tr class="even"><td><a href="document/drop_event"><code>drop</code></a></td><td><a href="globaleventhandlers/ondrop"><code>ondrop</code></a></td><td>…an item is dropped on a valid drop target. (See <a href="html_drag_and_drop_api/drag_operations#drop">Performing a Drop</a>.)</td></tr></tbody></table>

**Note:** Neither `dragstart` nor `dragend` events are fired when dragging a file into the browser from the OS.

Interfaces
----------

The HTML Drag and Drop interfaces are [`DragEvent`](dragevent), [`DataTransfer`](datatransfer), [`DataTransferItem`](datatransferitem) and [`DataTransferItemList`](datatransferitemlist).

The [`DragEvent`](dragevent) interface has a constructor and one [`dataTransfer`](dragevent/datatransfer) property, which is a [`DataTransfer`](datatransfer) object.

[`DataTransfer`](datatransfer) objects include the drag event's state, such as the type of drag being done (like `copy` or `move`), the drag's data (one or more items), and the MIME type of each *drag item*. [`DataTransfer`](datatransfer) objects also have methods to add or remove items to the drag's data.

The [`DragEvent`](dragevent) and [`DataTransfer`](datatransfer) interfaces should be the only ones needed to add HTML Drag and Drop capabilities to an application. (Firefox supports some [Gecko-specific extensions](#gecko_specific_interfaces) to the [`DataTransfer`](datatransfer) object, but those extensions will only work on Firefox.)

Each [`DataTransfer`](datatransfer) object contains an [`items`](datatransfer/items) property, which is a [`list`](datatransferitemlist) of [`DataTransferItem`](datatransferitem) objects. A [`DataTransferItem`](datatransferitem) object represents a single *drag item*, each with a [`kind`](datatransferitem/kind) property (either `string` or `file`) and a [`type`](datatransferitem/type) property for the data item's MIME type. The [`DataTransferItem`](datatransferitem) object also has methods to get the drag item's data.

The [`DataTransferItemList`](datatransferitemlist) object is a list of [`DataTransferItem`](datatransferitem) objects. The list object has methods to add a drag item to the list, remove a drag item from the list, and clear the list of all drag items.

A key difference between the [`DataTransfer`](datatransfer) and [`DataTransferItem`](datatransferitem) interfaces is that the former uses the synchronous [`getData()`](datatransfer/getdata) method to access a drag item's data, but the latter instead uses the asynchronous [`getAsString()`](datatransferitem/getasstring) method.

**Note:** [`DragEvent`](dragevent) and [`DataTransfer`](datatransfer) are broadly supported on desktop browsers. However, the [`DataTransferItem`](datatransferitem) and [`DataTransferItemList`](datatransferitemlist) interfaces have limited browser support. See [Interoperability](#interoperability) for more information about drag-and-drop interoperability.

### Gecko-specific interfaces

Mozilla and Firefox support some features not in the standard drag-and-drop model. These are *convenience functions* to help with dragging multiple items or non-string data (such as files). For more information, see [Dragging and Dropping Multiple Items](html_drag_and_drop_api/multiple_items). Additionally, see the [`DataTransfer`](datatransfer) reference page for all of the [Gecko-specific properties](datatransfer#gecko_properties) and [Gecko-specific methods](datatransfer#gecko_methods).

The basics
----------

This section is a summary of the basic steps to add drag-and-drop functionality to an application.

### Identify what is *draggable*

Making an element *draggable* requires adding the [`draggable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-draggable) attribute and the [`ondragstart`](globaleventhandlers/ondragstart) global event handler, as shown in the following code sample:

    <script>
      function dragstart_handler(ev) {
        // Add the target element's id to the data transfer object
        ev.dataTransfer.setData("text/plain", ev.target.id);
      }

      window.addEventListener('DOMContentLoaded', () => {
        // Get the element by id
        const element = document.getElementById("p1");
        // Add the ondragstart event listener
        element.addEventListener("dragstart", dragstart_handler);
      });
    </script>

    <p id="p1" draggable="true">This element is draggable.</p>

For more information, see:

-   [Draggable attribute reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/draggable)
-   [Drag operations guide](html_drag_and_drop_api/drag_operations#draggableattribute)

### Define the drag's data

The application is free to include any number of data items in a drag operation. Each data item is a [`string`](domstring) of a particular `type` — typically a MIME type such as `text/html`.

Each [`drag event`](dragevent) has a [`dataTransfer`](dragevent/datatransfer) property that *holds* the event's data. This property (which is a [`DataTransfer`](datatransfer) object) also has methods to *manage* drag data. The [`setData()`](datatransfer/setdata) method is used to add an item to the drag data, as shown in the following example.

    function dragstart_handler(ev) {
      // Add different types of drag data
      ev.dataTransfer.setData("text/plain", ev.target.innerText);
      ev.dataTransfer.setData("text/html", ev.target.outerHTML);
      ev.dataTransfer.setData("text/uri-list", ev.target.ownerDocument.location.href);
    }

-   For a list of common data types used in drag-and-drop (such as text, HTML, links, and files), see [Recommended Drag Types](html_drag_and_drop_api/recommended_drag_types).
-   For more information about drag data, see [Drag Data](html_drag_and_drop_api/drag_operations#dragdata).

### Define the drag image

By default, the browser supplies an image that appears beside the pointer during a drag operation. However, an application may define a custom image with the [`setDragImage()`](datatransfer/setdragimage) method, as shown in the following example.

    function dragstart_handler(ev) {
      // Create an image and then use it for the drag image.
      // NOTE: change "example.gif" to a real image URL or the image
      // will not be created and the default drag image will be used.
      let img = new Image();
      img.src = 'example.gif';
      ev.dataTransfer.setDragImage(img, 10, 10);
    }

Learn more about drag feedback images in:

-   [Setting the Drag Feedback Image](html_drag_and_drop_api/drag_operations#dragfeedback)

### Define the drag *effect*

The [`dropEffect`](datatransfer/dropeffect) property is used to control the feedback the user is given during a drag-and-drop operation. It typically affects which cursor the browser displays while dragging. For example, when the user hovers over a drop target, the browser's cursor may indicate the type of operation that will occur.

Three effects may be defined:

1.  `copy` indicates that the dragged data will be copied from its present location to the drop location.
2.  `move` indicates that the dragged data will be moved from its present location to the drop location.
3.  `link` indicates that some form of relationship or connection will be created between the source and drop locations.

During the drag operation, drag effects may be modified to indicate that certain effects are allowed at certain locations.

The following example shows how to use this property.

    function dragstart_handler(ev) {
      ev.dataTransfer.dropEffect = "copy";
    }

For more details, see:

-   [Drag Effects](html_drag_and_drop_api/drag_operations#drageffects)

### Define a *drop zone*

By default, the browser prevents anything from happening when dropping something onto most HTML elements. To change that behavior so that an element becomes a *drop zone* or is *droppable*, the element must have both [`ondragover`](globaleventhandlers/ondragover) and [`ondrop`](globaleventhandlers/ondrop) event handler attributes.

The following example shows how to use those attributes, and includes basic event handlers for each attribute.

    <script>
    function dragover_handler(ev) {
     ev.preventDefault();
     ev.dataTransfer.dropEffect = "move";
    }
    function drop_handler(ev) {
     ev.preventDefault();
     // Get the id of the target and add the moved element to the target's DOM
     const data = ev.dataTransfer.getData("text/plain");
     ev.target.appendChild(document.getElementById(data));
    }
    </script>

    <p id="target" ondrop="drop_handler(event)" ondragover="dragover_handler(event)">Drop Zone</p>

Note that each handler calls [`preventDefault()`](event/preventdefault) to prevent additional event processing for this event (such as [touch events](touch_events) or [pointer events](pointer_events)).

For more information, see:

-   [Specifying Drop Targets](html_drag_and_drop_api/drag_operations#droptargets)

### Handle the drop *effect*

The handler for the [`drop`](document/drop_event) event is free to process the drag data in an application-specific way.

Typically, an application uses the [`getData()`](datatransfer/getdata) method to retrieve drag items and then process them accordingly. Additionally, application semantics may differ depending on the value of the [`dropEffect`](datatransfer/dropeffect) and/or the state of modifier keys.

The following example shows a drop handler getting the source element's `id` from the drag data, and then using the `id` to move the source element to the drop element:

    <script>
    function dragstart_handler(ev) {
     // Add the target element's id to the data transfer object
     ev.dataTransfer.setData("application/my-app", ev.target.id);
     ev.dataTransfer.effectAllowed = "move";
    }
    function dragover_handler(ev) {
     ev.preventDefault();
     ev.dataTransfer.dropEffect = "move"
    }
    function drop_handler(ev) {
     ev.preventDefault();
     // Get the id of the target and add the moved element to the target's DOM
     const data = ev.dataTransfer.getData("application/my-app");
     ev.target.appendChild(document.getElementById(data));
    }
    </script>

    <p id="p1" draggable="true" ondragstart="dragstart_handler(event)">This element is draggable.</p>
    <div id="target" ondrop="drop_handler(event)" ondragover="dragover_handler(event)">Drop Zone</div>

For more information, see:

-   [Performing a Drop](html_drag_and_drop_api/drag_operations#drop)

### Drag end

At the end of a drag operation, the [`dragend`](document/dragend_event) event fires at the *source* element — the element that was the target of the drag start.

This event fires regardless of whether the drag completed or was canceled. The <span class="page-not-created">`dragend`</span> event handler can check the value of the [`dropEffect`](datatransfer/dropeffect) property to determine if the drag operation succeeded or not.

For more information about handling the end of a drag operation, see:

-   [Finishing a Drag](html_drag_and_drop_api/drag_operations#dragend)

Interoperability
----------------

As can be seen in the [DataTransferItem interface's Browser Compatibility table](datatransferitem#browser_compatibility), drag-and-drop interoperability is relatively broad among desktop browsers (except the [`DataTransferItem`](datatransferitem) and [`DataTransferItemList`](datatransferitemlist) interfaces have less support). This data also indicates drag-and-drop support among mobile browsers is very low.

Examples and demos
------------------

-   [Copying and moving elements with the `DataTransfer` interface](https://mdn.github.io/dom-examples/drag-and-drop/copy-move-DataTransfer.html)
-   [Copying and moving elements with the `DataTransferListItem` interface](https://mdn.github.io/dom-examples/drag-and-drop/copy-move-DataTransferItemList.html)
-   Dragging and dropping files (Firefox only): <https://jsfiddle.net/9C2EF/>
-   Dragging and dropping files (All browsers): [https://jsbin.com/hiqasek/](https://jsbin.com/hiqasek/edit?html,js,output)
-   A parking project using the Drag and Drop API: <https://park.glitch.me/> (You can edit [here](https://glitch.com/edit/#!/park))

Specifications
--------------

<table><thead><tr class="header"><th><strong>Specification</strong></th><th><strong>Status</strong></th><th><strong>Comment</strong></th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dnd">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

See also
--------

-   <a href="html_drag_and_drop_api/drag_operations" class="internal">Drag Operations</a>
-   <a href="html_drag_and_drop_api/multiple_items" class="internal">Dragging and Dropping Multiple Items</a>
-   <a href="html_drag_and_drop_api/recommended_drag_types" class="internal">Recommended Drag Types</a>
-   [HTML5 Living Standard: Drag and Drop](https://html.spec.whatwg.org/multipage/interaction.html#dnd)
-   [Drag and Drop interoperability data from CanIUse](https://caniuse.com/#search=draganddrop)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API</a>
