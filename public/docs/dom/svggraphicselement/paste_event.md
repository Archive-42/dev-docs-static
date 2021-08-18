SVGGraphicsElement: paste event
===============================

The `paste` event is fired on an [`SVGGraphicsElement`](../svggraphicselement) when the user has initiated a "paste" action through the browser's user interface.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../clipboardevent"><code>ClipboardEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>onpaste</code></span></td></tr></tbody></table>

If the cursor is in an editable context (for example, in a [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) or an element with `contenteditable` attribute set to `true`) then the default action is to insert the contents of the clipboard into the document at the cursor position.

A handler for this event can access the clipboard contents by calling [`getData()`](../datatransfer/getdata) on the event's `clipboardData` property.

To override the default behavior (for example to insert some different data or a transformation of the clipboard contents) an event handler must cancel the default action using [`event.preventDefault()`](../event/preventdefault), and then insert its desired data manually.

It's possible to construct and dispatch a [synthetic](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events) `paste` event, but this will not affect the document's contents.

Example
-------

### HTML

    <?xml version="1.0" encoding="UTF-8"?>
    <svg viewBox="0 0 140 30" width="600" height="320" xmlns="http://www.w3.org/2000/svg">
        <foreignObject x="5" y="-10" width="90" height="20">
            <input xmlns="http://www.w3.org/1999/xhtml" value="Copy this text"/>
        </foreignObject>
        <text x="5" y="30" id="element-to-paste-text" tabindex="1">Paste it here</text>
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

    document.getElementById("element-to-paste-text").addEventListener("paste", evt => {
      evt.target.textContent = evt.clipboardData.getData("text/plain").toUpperCase();
      evt.preventDefault();
    });

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/types.html#SVGDOMDependencies">Scalable Vector Graphics (SVG) 2</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Definition that the clipboard events apply to SVG elements.</td></tr><tr class="even"><td><a href="https://w3c.github.io/clipboard-apis/#clipboard-event-paste">Clipboard API and events</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.SVGGraphicsElement.paste_event`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   Related events: `cut`, `copy`
-   This event on HTML [`Element`](../element) targets: `paste`
-   This event on [`Document`](../document) targets: `paste`
-   This event on [`Window`](../window) targets: `paste`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGGraphicsElement/paste_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGGraphicsElement/paste_event</a>
