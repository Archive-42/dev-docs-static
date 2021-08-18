HTMLElement: beforeinput event
==============================

The DOM `beforeinput` event fires when the value of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element is about to be modified. The event also applies to elements with [`contenteditable`](contenteditable) enabled, and to any element when [`designMode`](../document/designmode) is turned on.

This allows web apps to override text edit behavior before the browser modifies the DOM tree, and provides more control over input events to improve performance.

In the case of `contenteditable` and `designMode`, the event target is the **editing host**. If these properties apply to multiple elements, the editing host is the nearest ancestor element whose parent isn't editable.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../inputevent"><code>InputEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td>None</td></tr><tr class="odd"><td>Sync / Async</td><td>Sync</td></tr><tr class="even"><td>Composed</td><td>Yes</td></tr><tr class="odd"><td>Default Action</td><td>Update the DOM element</td></tr></tbody></table>

Examples
--------

### Feature Detection

The following function returns true if `beforeinput`, and thus `getTargetRanges`, is supported.

    function isBeforeInputEventAvailable() {
      return window.InputEvent && typeof InputEvent.prototype.getTargetRanges === "function";
    }

### Simple logger

This example logs the current value of the element, immediately before replacing that value with the new one applied to the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element.

#### HTML

    <input placeholder="Enter some text" name="name"/>
    <p id="values"></p>

#### JavaScript

    const input = document.querySelector('input');
    const log = document.getElementById('values');

    input.addEventListener('beforeinput', updateValue);

    function updateValue(e) {
      log.textContent = e.target.value;
    }

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-beforeinput">UI Events<br />
<span class="small">The definition of 'beforeinput event' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`beforeinput_event`

Yes

79

87

74-87

No

Yes

Yes

Yes

Yes

87

79-87

Yes

Yes

Yes

See also
--------

-   Related event: `input`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/beforeinput_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/beforeinput_event</a>
