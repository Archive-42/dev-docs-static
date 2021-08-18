# Document: cut event

The `cut` event is fired when the user has initiated a "cut" action through the browser's user interface.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../clipboardevent"><code>ClipboardEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../htmlelement/oncut"><code>oncut</code></a></td></tr></tbody></table>

The original target for this event is the [`Element`](../element) that was the intended target of the cut action. You can listen for this event on the [`Document`](../document) interface to handle it in the capture or bubbling phases. For full details on this event please see the page on the [Element: cut event](../element/cut_event).

## Examples

    document.addEventListener('cut', (event) => {
        console.log('cut action initiated')
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#clipboard-event-cut">Clipboard API and events</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`cut_event`

1

≤18

Yes

No

15

Yes

1

18

Yes

14

?

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

?

7.0

## See also

- Related events: [`copy`](copy_event), [`paste`](paste_event)
- This event on [`Element`](../element) targets: [`cut`](../element/cut_event)
- This event on [`Window`](../window) targets: [`cut`](../window/cut_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/cut_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/cut_event</a>
