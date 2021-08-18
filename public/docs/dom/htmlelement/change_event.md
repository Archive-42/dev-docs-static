HTMLElement: change event
=========================

The `change` event is fired for [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), and [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) elements when an alteration to the element's value is committed by the user. Unlike the [`input`](input_event) event, the `change` event is not necessarily fired for each alteration to an element's `value`.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onchange"><code>onchange</code></a></td></tr></tbody></table>

Depending on the kind of element being changed and the way the user interacts with the element, the `change` event fires at a different moment:

-   When the element is `:checked` (by clicking or using the keyboard) for `<input type="radio">` and `<input type="checkbox">`;
-   When the user commits the change explicitly (e.g., by selecting a value from a [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)'s dropdown with a mouse click, by selecting a date from a date picker for `<input type="date">`, by selecting a file in the file picker for `<input type="file">`, etc.);
-   When the element loses focus after its value was changed, but not committed (e.g., after editing the value of [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) or `<input type="text">`).

The HTML specification lists [the `<input>` types that should fire the `change` event](https://html.spec.whatwg.org/multipage/forms.html#concept-input-apply).

Examples
--------

### &lt;select&gt; element

#### HTML

    <label>Choose an ice cream flavor:
      <select class="ice-cream" name="ice-cream">
        <option value="">Select One …</option>
        <option value="chocolate">Chocolate</option>
        <option value="sardine">Sardine</option>
        <option value="vanilla">Vanilla</option>
      </select>
    </label>

    <div class="result"></div>

#### JavaScript

    const selectElement = document.querySelector('.ice-cream');

    selectElement.addEventListener('change', (event) => {
      const result = document.querySelector('.result');
      result.textContent = `You like ${event.target.value}`;
    });

#### Result

### Text input element

For some elements, including `<input type="text">`, the `change` event doesn't fire until the control loses focus. Try entering something into the field below, and then click somewhere else to trigger the event.

#### HTML

    <input placeholder="Enter some text" name="name"/>
    <p id="log"></p>

#### JavaScript

    const input = document.querySelector('input');
    const log = document.getElementById('log');

    input.addEventListener('change', updateValue);

    function updateValue(e) {
      log.textContent = e.target.value;
    }

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-change">HTML Living Standard<br />
<span class="small">The definition of 'change' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`change_event`

1

12

1

9

9

3

1

18

4

10.1

1

1.0

Different browsers do not always agree whether a `change` event should be fired for certain types of interaction. For example, keyboard navigation in [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) elements used to never fire a `change` event in Gecko until the user hit Enter or switched the focus away from the `<select>` (see [bug 126379](https://bugzilla.mozilla.org/show_bug.cgi?id=126379)). Since Firefox 63 (Quantum), this behavior is consistent between all major browsers, however.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event</a>
