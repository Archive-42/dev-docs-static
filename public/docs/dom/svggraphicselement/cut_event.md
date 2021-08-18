SVGGraphicsElement: cut event
=============================

The `cut` event is fired on an [`SVGGraphicsElement`](../svggraphicselement) when the user has initiated a "cut" action through the browser's user interface.

If the user attempts a cut action on uneditable content, the `cut` event still fires but the event object contains no data.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../clipboardevent"><code>ClipboardEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>oncut</code></span></td></tr></tbody></table>

The event's default action is to copy the current selection (if any) to the system clipboard and remove it from the document.

A handler for this event can *modify* the clipboard contents by calling [`setData(format, data)`](../datatransfer/setdata) on the event's [`ClipboardEvent.clipboardData`](../clipboardevent/clipboarddata) property, and cancelling the default action using `event.preventDefault()`.

Note though that cancelling the default action will also prevent the document from being updated. So an event handler which wants to emulate the default action for "cut" while modifying the clipboard must also manually remove the selection from the document.

The handler cannot *read* the clipboard data.

It's possible to construct and dispatch a [synthetic](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events) `cut` event, but this will not affect the system clipboard or the document's contents.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/types.html#SVGDOMDependencies">Scalable Vector Graphics (SVG) 2</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Definition that the clipboard events apply to SVG elements.</td></tr><tr class="even"><td><a href="https://w3c.github.io/clipboard-apis/#clipboard-event-cut">Clipboard API and events</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.SVGGraphicsElement.cut_event`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   Related events: `copy`, `paste`
-   This event on HTML [`Element`](../element) targets: `cut`
-   This event on [`Document`](../document) targets: `cut`
-   This event on [`Window`](../window) targets: `cut`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGGraphicsElement/cut_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGGraphicsElement/cut_event</a>
