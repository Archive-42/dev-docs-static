Element: cut event
==================

The `cut` event is fired when the user has initiated a "cut" action through the browser's user interface.

If the user attempts a cut action on uneditable content, the `cut` event still fires but the event object contains no data.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../clipboardevent"><code>ClipboardEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../htmlelement/oncut"><code>oncut</code></a></td></tr></tbody></table>

The event's default action is to copy the current selection (if any) to the system clipboard and remove it from the document.

A handler for this event can *modify* the clipboard contents by calling [`setData(format, data)`](../datatransfer/setdata) on the event's [`ClipboardEvent.clipboardData`](../clipboardevent/clipboarddata) property, and cancelling the default action using [`event.preventDefault()`](../event/preventdefault).

Note though that cancelling the default action will also prevent the document from being updated. So an event handler which wants to emulate the default action for "cut" while modifying the clipboard must also manually remove the selection from the document.

The handler cannot *read* the clipboard data.

It's possible to construct and dispatch a [synthetic](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events) `cut` event, but this will not affect the system clipboard or the document's contents.

Examples
--------

### Live example

#### HTML

    <div class="source" contenteditable="true">Try cutting text from this box...</div>
    <div class="target" contenteditable="true">...and pasting it into this one</div>

#### JS

    const source = document.querySelector('div.source');

    source.addEventListener('cut', (event) => {
        const selection = document.getSelection();
        event.clipboardData.setData('text/plain', selection.toString().toUpperCase());
        selection.deleteFromDocument();
        event.preventDefault();
    });

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#clipboard-event-cut">Clipboard API and events</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

Browser compatibility
---------------------

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

`cut_event`

1

≤18

Yes

Yes

15

Yes

1

18

Yes

14

Yes

1.0

`clipboardData`

58

≤18

22

No

45

Yes

58

58

22

43

Yes

7.0

See also
--------

-   Related events: [`copy`](copy_event), [`paste`](paste_event)
-   This event on [`Document`](../document) targets: [`cut`](../document/cut_event)
-   This event on [`Window`](../window) targets: [`cut`](../window/copy_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/cut_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/cut_event</a>
