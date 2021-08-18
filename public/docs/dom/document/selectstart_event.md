# Document: selectstart event

The `selectstart` event of the [Selection API](../selection) is fired when a user starts a new selection.

If the event is canceled, the selection is not changed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onselectstart"><code>onselectstart</code></a></td></tr></tbody></table>

## Examples

    // addEventListener version
    document.addEventListener('selectstart', () => {
      console.log('Selection started');
    });

    // onselectstart version
    document.onselectstart = () => {
      console.log('Selection changed.');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#selectstart-event">Selection API<br />
<span class="small">The definition of 'selectstart' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`selectstart_event`

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

No

Yes

## See also

- [`selectionchange`](selectionchange_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/selectstart_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/selectstart_event</a>
