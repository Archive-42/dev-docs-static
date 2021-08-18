# Element: MSManipulationStateChanged event

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`MSManipulationStateChanged` fires when the state of an element being manipulated has changed (ie. whenever you start or finish panning or zooming an element).

It is a proprietary event specific to Microsoft Edge and Internet Explorer.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Unknown</td></tr><tr class="even"><td>Cancelable</td><td>Unknown</td></tr><tr class="odd"><td>Interface</td><td><a href="../msmanipulationevent"><code>MSManipulationEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td>Unknown</td></tr></tbody></table>

Get manipulation states using the `lastState `and `currentState `properties.

## Examples

    // Listen for panning state change events
    outerScroller.addEventListener("MSManipulationStateChanged", function(e) {
        // Check to see if they lifted while pulled to the top
        if (e.currentState == MS_MANIPULATION_STATE_INERTIA &&
            outerScroller.scrollTop === 0) {
            refreshItemsAsync();
        }
    });

## Specifications

Not part of any specification.

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

`MSManipulationStateChanged_event`

No

12-79

No

Yes

No

No

No

No

No

No

No

No

## See also

- [`MSManipulationEvent`](../msmanipulationevent)
- [Microsoft API extensions](../microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/MSManipulationStateChanged_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/MSManipulationStateChanged_event</a>
