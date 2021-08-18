# Document: selectionchange event

The `selectionchange` event of the [Selection API](../selection) is fired when the current text selection on a document is changed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onselectionchange"><code>onselectionchange</code></a></td></tr></tbody></table>

## Examples

    // addEventListener version
    document.addEventListener('selectionchange', () => {
      console.log(document.getSelection());
    });

    // onselectionchange version
    document.onselectionchange = () => {
      console.log(document.getSelection());
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#selectionchange-event">Selection API<br />
<span class="small">The definition of 'selectionchange' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`selectionchange_event`

Yes

12

52

Yes

?

1.3

Yes

Yes

52

?

Yes

Yes

## See also

- [`selectstart`](selectstart_event)
- [`Document.getSelection()`](getselection)
- [`Selection`](../selection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/selectionchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/selectionchange_event</a>
