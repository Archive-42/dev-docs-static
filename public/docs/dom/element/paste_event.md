# Element: paste event

The `paste` event is fired when the user has initiated a "paste" action through the browser's user interface.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../clipboardevent"><code>ClipboardEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../htmlelement/onpaste"><code>onpaste</code></a></td></tr></tbody></table>

If the cursor is in an editable context (for example, in a [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) or an element with `contenteditable` attribute set to `true`) then the default action is to insert the contents of the clipboard into the document at the cursor position.

A handler for this event can access the clipboard contents by calling [`getData()`](../datatransfer/getdata) on the event's `clipboardData` property.

To override the default behavior (for example to insert some different data or a transformation of the clipboard contents) an event handler must cancel the default action using [`event.preventDefault()`](../event/preventdefault), and then insert its desired data manually.

It's possible to construct and dispatch a [synthetic](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events) `paste` event, but this will not affect the document's contents.

## Examples

### Live example

#### HTML

    <div class="source" contenteditable="true">Try copying text from this box...</div>
    <div class="target" contenteditable="true">...and pasting it into this one</div>

#### JS

    const target = document.querySelector('div.target');

    target.addEventListener('paste', (event) => {
        let paste = (event.clipboardData || window.clipboardData).getData('text');
        paste = paste.toUpperCase();

        const selection = window.getSelection();
        if (!selection.rangeCount) return false;
        selection.deleteFromDocument();
        selection.getRangeAt(0).insertNode(document.createTextNode(paste));

        event.preventDefault();
    });

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#clipboard-event-paste">Clipboard API and events</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`paste_event`

1

12

22

8

Before Internet Explorer 11, copying files does not trigger the `paste` event.

15

5

1

18

22

14

4.2

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

## See also

- Related events: [`cut`](cut_event), [`copy`](copy_event)
- This event on [`Document`](../document) targets: [`paste`](../document/paste_event)
- This event on [`Window`](../window) targets: [`paste`](../window/paste_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/paste_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/paste_event</a>
