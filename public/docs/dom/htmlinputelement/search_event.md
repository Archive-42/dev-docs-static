HTMLInputElement: search event
==============================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `search` event is fired when a search is initiated using an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element of `type="search"`.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onsearch</code></td></tr></tbody></table>

There are several ways a search can be initiated, such as by pressing Enter while the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) is focused, or, if the [`incremental`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-incremental) attribute is present, after a UA-defined timeout elapses since the most recent keystroke (with new keystrokes resetting the timeout so the firing of the event is debounced).

Current UA implementations of `<input type="search">` have an additional control to clear the field. Using this control also fires the `search` event. In that case the `value` of the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element will be the empty string.

Examples
--------

    // addEventListener version
    const input = document.querySelector('input[type="search"]');

    input.addEventListener('search', () => {
     console.log("The term searched for was " + input.value);
    })

    // onsearch version
    const input = document.querySelector('input[type="search"]');

    input.onsearch = () => {
     console.log("The term searched for was " + input.value);
    })

Specifications
--------------

This event is not part of any specification.

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

`search_event`

Yes

79

No

No

Yes

Yes

Yes

Yes

No

?

?

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/search_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/search_event</a>
