HTMLElement: input event
========================

The `input` event fires when the `value` of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element has been changed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../inputevent"><code>InputEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/oninput"><code>GlobalEventHandlers.oninput</code></a></td></tr></tbody></table>

The event also applies to elements with [`contenteditable`](contenteditable) enabled, and to any element when [`designMode`](../document/designmode) is turned on. In the case of `contenteditable` and `designMode`, the event target is the *editing host*. If these properties apply to multiple elements, the editing host is the nearest ancestor element whose parent isn't editable.

For `<input>` elements with `type=checkbox` or `type=radio`, the `input` event should fire whenever a user toggles the control, per [the HTML5 specification](https://html.spec.whatwg.org/multipage/input.html#the-input-element:event-input-2). However, historically this has not always been the case. Check compatibility, or use the [`change`](change_event) event instead for elements of these types.

**Note:** The `input` event is fired every time the `value` of the element changes. This is unlike the [`change`](change_event) event, which only fires when the value is committed, such as by pressing the enter key, selecting a value from a list of options, and the like.

Examples
--------

This example logs the value whenever you change the value of the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element.

### HTML

    <input placeholder="Enter some text" name="name"/>
    <p id="values"></p>

### JavaScript

    const input = document.querySelector('input');
    const log = document.getElementById('values');

    input.addEventListener('input', updateValue);

    function updateValue(e) {
      log.textContent = e.target.value;
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#event-input-input">HTML Living Standard<br />
<span class="small">The definition of 'input event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-input">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'input event' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`input_event`

1

79

12-79

Not supported on `select`, `checkbox`, or `radio` inputs.

6

9

Only supports `input` of type `text` and `password`.

11.6

3.1

1

18

6

12

2

1.0

See also
--------

-   Related events
    -   [`beforeinput`](beforeinput_event)
    -   [`change`](change_event)
    -   [`invalid`](../htmlinputelement/invalid_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event</a>
