SVGGraphicsElement: copy event
==============================

The `copy` event fires on [`SVGGraphicsElements`](../svggraphicselement) when the user initiates a copy action through the browser's user interface.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../clipboardevent"><code>ClipboardEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>oncopy</code></span></td></tr></tbody></table>

The event's default action is to copy the selection (if any) to the clipboard.

A handler for this event can *modify* the clipboard contents by calling [`setData(format, data)`](../datatransfer/setdata) on the event's [`ClipboardEvent.clipboardData`](../clipboardevent/clipboarddata) property, and cancelling the event's default action using `event.preventDefault()`.

However, the handler cannot *read* the clipboard data.

It's possible to construct and dispatch a [synthetic](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events) `copy` event, but this will not affect the system clipboard.

Example
-------

### HTML

    <?xml version="1.0" encoding="UTF-8"?>
    <svg viewBox="0 0 100 30" width="600" height="320" xmlns="http://www.w3.org/2000/svg">
        <text x="5" y="10" id="text-to-copy">Copy this text</text>
        <foreignObject x="5" y="20" width="90" height="20">
            <input xmlns="http://www.w3.org/1999/xhtml" placeholder="Paste it here"/>
        </foreignObject>
    </svg>

### CSS

    input {
      font-size: 10px;
      width: 100%;
      height: 90%;
      box-sizing: border-box;
      border: 1px solid black;
    }

### JavaScript

    document.getElementsByTagName("text")[0].addEventListener("copy", evt => {
      evt.clipboardData.setData('text/plain', document.getSelection().toString().toUpperCase());
      evt.preventDefault();
    });

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/types.html#SVGDOMDependencies">Scalable Vector Graphics (SVG) 2</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Definition that the clipboard events apply to SVG elements.</td></tr><tr class="even"><td><a href="https://w3c.github.io/clipboard-apis/#clipboard-event-copy">Clipboard API and events</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.SVGGraphicsElement.copy_event`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   Related events: `cut`, `paste`
-   This event on HTML [`Element`](../element) targets: `copy`
-   This event on [`Document`](../document) targets: `copy`
-   This event on [`Window`](../window) targets: `copy`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGGraphicsElement/copy_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGGraphicsElement/copy_event</a>
