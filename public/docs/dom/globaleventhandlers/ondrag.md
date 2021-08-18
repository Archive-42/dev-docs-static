# GlobalEventHandlers.ondrag

A [`global event handler`](../globaleventhandlers) for the `drag` event.

## Syntax

    var dragHandler = targetElement.ondrag;

### Return value

`dragHandler`  
The _drag_ event handler for element `targetElement`.

## Example

This example includes the use of the _ondrag_ attribute handler to set an element's _drag_ event handler.

    <!DOCTYPE html>
    <html lang=en>
    <title>Examples of using the ondrag Global Event Attribute</title>
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
    function drag_handler(ev) {
     console.log("Drag");
    }

    function dragstart_handler(ev) {
     console.log("dragStart");
     ev.dataTransfer.setData("text", ev.target.id);
    }

    function drop_handler(ev) {
     console.log("Drop");
     ev.currentTarget.style.background = "lightyellow";

     ev.preventDefault();
     var data = ev.dataTransfer.getData("text");
     ev.target.appendChild(document.getElementById(data));
    }

    function dragover_handler(ev) {
     console.log("dragOver");
     ev.preventDefault();
    }
    </script>
    <body>
    <h1>Examples of <code>ondrag</code>, <code>ondrop</code>, <code>ondragstart</code>, <code>ondragover</code></h1>
     <div> <!-- <div class="source"> -->
       <p id="source" ondrag="drag_handler(event);" ondragstart="dragstart_handler(event);" draggable="true">
         Select this element, drag it to the Drop Zone and then release the selection to move the element.</p>
     </div>
     <div id="target" ondrop="drop_handler(event);" ondragover="dragover_handler(event);">Drop Zone</div>
    </body>
    </html>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#ix-handler-ondrag">HTML Living Standard<br />
<span class="small">The definition of 'ondrag' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/index.html#ix-handler-ondrag">HTML 5.1<br />
<span class="small">The definition of 'ondrag' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`ondrag`

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

- `drag`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondrag" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondrag</a>
