Element: copy event
===================

The `copy` event fires when the user initiates a copy action through the browser's user interface.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../clipboardevent"><code>ClipboardEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../htmlelement/oncopy"><code>oncopy</code></a></td></tr></tbody></table>

The event's default action is to copy the selection (if any) to the clipboard.

A handler for this event can *modify* the clipboard contents by calling [`setData(format, data)`](../datatransfer/setdata) on the event's [`ClipboardEvent.clipboardData`](../clipboardevent/clipboarddata) property, and cancelling the event's default action using [`event.preventDefault()`](../event/preventdefault).

However, the handler cannot *read* the clipboard data.

It's possible to construct and dispatch a [synthetic](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events) `copy` event, but this will not affect the system clipboard.

Examples
--------

### Live example

#### HTML

    <div class="source" contenteditable="true">Try copying text from this box...</div>
    <div class="target" contenteditable="true">...and pasting it into this one</div>

#### JS

    const source = document.querySelector('div.source');

    source.addEventListener('copy', (event) => {
        const selection = document.getSelection();
        event.clipboardData.setData('text/plain', selection.toString().toUpperCase());
        event.preventDefault();
    });

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#clipboard-event-copy">Clipboard API and events</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`copy_event`

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

-   Related events: [`cut`](cut_event), [`paste`](paste_event)
-   This event on [`Document`](../document) targets: [`copy`](../document/copy_event)
-   This event on [`Window`](../window) targets: [`copy`](../window/copy_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/copy_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/copy_event</a>
