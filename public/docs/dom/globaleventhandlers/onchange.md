# GlobalEventHandlers.onchange

The `onchange` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `change` events.

`change` events fire when the user commits a value change to a form control. This may be done, for example, by clicking outside of the control or by using the Tab key to switch to a different control.

**Note:** Unlike [`oninput`](oninput), the `onchange` event handler is not necessarily called for each alteration to an element's `value`.

## Syntax

    target.onchange = functionRef;

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives an [`Event`](../event) object as its sole argument.

## Example

This example logs the number of characters in an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element, every time you modify its contents and then change focus away from it.

### HTML

    <input type="text" placeholder="Type something here, then click outside of the field." size="50">
    <p id="log"></p>

### JavaScript

    let input = document.querySelector('input');
    let log = document.getElementById('log');

    input.onchange = handleChange;

    function handleChange(e) {
      log.textContent = `The field's value is
          ${e.target.value.length} character(s) long.`;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onchange">HTML Living Standard<br />
<span class="small">The definition of 'onchange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onchange`

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

## See also

- `change` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onchange</a>
