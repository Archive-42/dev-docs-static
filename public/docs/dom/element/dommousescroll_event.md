# Element: DOMMouseScroll event

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The DOM `DOMMouseScroll` event is fired asynchronously when mouse wheel or similar device is operated and the accumulated scroll amount is over 1 line or 1 page since last event. It's represented by the [`MouseScrollEvent`](../mousescrollevent) interface. This event was only implemented by Firefox. You should instead use the standard [`wheel`](wheel_event) event.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../mousescrollevent"><code>MouseScrollEvent</code></a> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td></tr></tbody></table>

If you want to prevent the default action of mouse wheel events, it's not enough to handle only this event on Gecko because If scroll amount by a native mouse wheel event is less than 1 line (or less than 1 page when the system setting is by page scroll), other mouse wheel events may be fired without this event.

On Gecko 17 (Firefox 17) or later, you need to call `preventDefault()` of `wheel` events which must be fired for every native event.

Use the standardized `wheel` event if available.

## Properties

The event has only one additional property beyond standard events.

### detail

The `detail` property describes the scroll more precisely, with positive values indicating scrolling downward and negative values indicating scrolling upward.

If the event represents scrolling up by a page, the value of `detail` is -32768. If the event indicates scrolling down by a page, the value is +32768. Any other value represents the number of lines to scroll, with the direction indicated by the value's sign.

**Note:** Trusted events are never sent with a value of 0 for `detail`.

Trusted events are never fired with 0.

**Note:** If the platform's native mouse wheel events only provide scroll distance by pixels, or if the speed can be customized by the user, the value is computed using the line height of the nearest scrollable ancestor element of the event's target. If that element's font size is smaller than `mousewheel.min_line_scroll_amount`, that preference's value is used as the line height.

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

`DOMMouseScroll_event`

No

No

1

No

No

No

No

No

4

No

No

No

## See also

- [`MouseScrollEvent`](../mousescrollevent)
- Gecko's legacy pixel scroll event: `MozMousePixelScroll`
- Non-Gecko browsers' legacy mouse wheel event: `mousewheel`
- Standardized wheel event: `wheel`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/DOMMouseScroll_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/DOMMouseScroll_event</a>
