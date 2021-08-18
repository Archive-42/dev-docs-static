File drag and drop
==================

HTML Drag and Drop interfaces enable web applications to drag and drop files on a web page. This document describes how an application can accept one or more files that are dragged from the underlying platform's *file manager* and dropped on a web page.

The main steps to drag and drop are to define a *drop zone* (i.e. a target element for the file drop) and to define event handlers for the `drop` and `dragover` events. These steps are described below, including example code snippets. The full source code is available in [MDN's drag-and-drop repository](https://github.com/mdn/dom-examples/tree/master/drag-and-drop) (pull requests and/or issues are welcome).

Note: [`HTML drag and drop`](../html_drag_and_drop_api) defines two different APIs to support dragging and dropping files. One API is the [`DataTransfer`](../datatransfer) interface and the second API is the [`DataTransferItem`](../datatransferitem) and [`DataTransferItemList`](../datatransferitemlist) interfaces. This example illustrates the use of both APIs (and does not use any Gecko specific interfaces).

Define the drop *zone*
----------------------

The *target element* of the `drop` event needs an [`ondrop`](../globaleventhandlers/ondrop) global event handler. The following code snippet shows how this is done with a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element:

    <div id="drop_zone" ondrop="dropHandler(event);">
      <p>Drag one or more files to this Drop Zone ...</p>
    </div>

Typically, an application will include a `dragover` event handler on the drop target element and that handler will turn off the browser's default drag behavior. To add this handler, you need to include a [`ondragover`](../globaleventhandlers/ondragover) global event handler:

    <div id="drop_zone" ondrop="dropHandler(event);" ondragover="dragOverHandler(event);">
      <p>Drag one or more files to this Drop Zone ...</p>
    </div>

Lastly, an application may want to style the drop target element to visually indicate the element is a drop zone. In this example, the drop target element uses the following styling:

    #drop_zone {
      border: 5px solid blue;
      width:  200px;
      height: 100px;
    }

Note that `dragstart` and `dragend` events are not fired when dragging a file into the browser from the OS.

Process the drop
----------------

The `drop` event is fired when the user drops the file(s). In the following drop handler, if the browser supports [`DataTransferItemList`](../datatransferitemlist) interface, the [`getAsFile()`](../datatransferitem/getasfile) method is used to access each file; otherwise the [`DataTransfer`](../datatransfer) interface's [`files`](../datatransfer/files) property is used to access each file.

This example shows how to write the name of each dragged file to the console. In a *real* application, an application may want to process a file using the [`File API`](../file).

Note that in this example, any drag item that is not a file is ignored.

    function dropHandler(ev) {
      console.log('File(s) dropped');

      // Prevent default behavior (Prevent file from being opened)
      ev.preventDefault();

      if (ev.dataTransfer.items) {
        // Use DataTransferItemList interface to access the file(s)
        for (var i = 0; i < ev.dataTransfer.items.length; i++) {
          // If dropped items aren't files, reject them
          if (ev.dataTransfer.items[i].kind === 'file') {
            var file = ev.dataTransfer.items[i].getAsFile();
            console.log('... file[' + i + '].name = ' + file.name);
          }
        }
      } else {
        // Use DataTransfer interface to access the file(s)
        for (var i = 0; i < ev.dataTransfer.files.length; i++) {
          console.log('... file[' + i + '].name = ' + ev.dataTransfer.files[i].name);
        }
      }
    }

Prevent the browser's default drag behavior
-------------------------------------------

The following `dragover` event handler calls [`preventDefault()`](../event/preventdefault) to turn off the browser's default drag and drop handler.

    function dragOverHandler(ev) {
      console.log('File(s) in drop zone');

      // Prevent default behavior (Prevent file from being opened)
      ev.preventDefault();
    }

See also
--------

-   [HTML Drag and Drop API](../html_drag_and_drop_api)
-   <a href="drag_operations" class="internal">Drag Operations</a>
-   [HTML5 Living Standard: Drag and Drop](https://html.spec.whatwg.org/multipage/interaction.html#dnd)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API/File_drag_and_drop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API/File_drag_and_drop</a>