# Document: pointerlockchange event

The `pointerlockchange` event is fired when the pointer is locked/unlocked.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>onpointerlockchange</code></span></td></tr></tbody></table>

## Examples

Using `addEventListener()`:

    document.addEventListener('pointerlockchange', (event) => {
      console.log('Pointer lock changed');
    });

Using the `onpointerlockchange` event handler property:

    document.onpointerlockchange = (event) => {
      console.log('Pointer lock changed');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/pointerlock/#pointerlockchange-and-pointerlockerror-events">Pointer Lock</a></td><td><span class="spec-cr">Candidate Recommendation</span></td></tr></tbody></table>

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

`pointerlockchange_event`

45

22-45

≤79

?

?

?

?

45

≤37-45

45

25-45

?

?

?

5.0

1.5-5.0

## See also

- [Using Pointer Lock API](../pointer_lock_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerlockchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerlockchange_event</a>
