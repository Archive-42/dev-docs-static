# GlobalEventHandlers.ondragleave

A [`global event handler`](../globaleventhandlers) for the `dragleave` event.

## Syntax

    var dragleaveHandler = targetElement.ondragleave;

### Return value

`dragleaveHandler`  
The _dragleave_ event handler for element `targetElement`.

## Example

This example demonstrates using the [`ondragleave`](ondragleave) attribute handler to set an element's `dragleave` event handler.

    <!DOCTYPE html>
    <html lang=en>
    <title>Examples of using the Drag and Drop Global Event Attribute</title>
    <meta content="width=device-width">
    <style>
      div {
        margin: 0em;
        padding: 2em;
      }
      #source {
        color: blue;
        border: 1px solid black;
      }
      #target {
        border: 1px solid black;
      }
    </style>
    </head>
    <script>
    function dragstart_handler(ev) {
     console.log("dragStart");
     // Change the source element's border to signify drag has started
     ev.currentTarget.style.border = "dashed";
     ev.dataTransfer.setData("text", ev.target.id);
    }

    function dragover_handler(ev) {
     console.log("dragOver");
     // Change the target element's background color to signify a drag over event
     // has occurred
     ev.currentTarget.style.background = "lightblue";
     ev.preventDefault();
    }

    function drop_handler(ev) {
     console.log("Drop");
     ev.preventDefault();
     var data = ev.dataTransfer.getData("text");
     ev.target.appendChild(document.getElementById(data));
    }

    function dragenter_handler(ev) {
     console.log("dragEnter");
     // Change the source element's background color for enter events
     ev.currentTarget.style.background = "yellow";
    }

    function dragleave_handler(ev) {
     console.log("dragLeave");
     // Change the source element's background color back to white
     ev.currentTarget.style.background = "white";
    }

    function dragend_handler(ev) {
     console.log("dragEnd");
     // Change the target element's background color to visually indicate
     // the drag ended.
     var el=document.getElementById("target");
     el.style.background = "pink";
    }

    function dragexit_handler(ev) {
     console.log("dragExit");
     // Change the source element's background color back to green to signify a dragexit event
     ev.currentTarget.style.background = "green";
    }

    function init() {
     // Set handlers for the source's enter/leave/end/exit events
     var el=document.getElementById("source");
     el.ondragenter = dragenter_handler;
     el.ondragleave = dragleave_handler;
     el.ondragend = dragend_handler;
     el.ondragexit = dragexit_handler;
    }
    </script>
    <body onload="init();">
    <h1>Examples of <code>ondragenter</code>, <code>ondragleave</code>, <code>ondragend</code>, <code>ondragexit</code></h1>
     <div>
       <p id="source" ondragstart="dragstart_handler(event);" draggable="true">
         Select this element, drag it to the Drop Zone and then release the selection to move the element.</p>
     </div>
     <div id="target" ondrop="drop_handler(event);" ondragover="dragover_handler(event);">Drop Zone</div>
    </body>
    </html>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#ix-handler-ondragleave">HTML Living Standard<br />
<span class="small">The definition of 'ondragleave' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/index.html#ix-handler-ondragleave">HTML 5.1<br />
<span class="small">The definition of 'ondragleave' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`ondragleave`

1

12

9

9

12

3.1

1

18

9

12

2

1.0

## See also

- `dragleave`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragleave" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragleave</a>
