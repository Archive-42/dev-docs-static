# GlobalEventHandlers.onfocus

The `onfocus` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `focus` events on the given element.

The `focus` event is raised when the user sets focus on an element.

For `onfocus` to fire on non-input elements, they must be given the [`tabindex`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-tabindex) attribute (see [Building keyboard accessibility back in](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#building_keyboard_accessibility_back_in) for more details).

**Note:** The opposite of `onfocus` is [`onblur`](onblur).

## Syntax

    target.onfocus = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`FocusEvent`](../focusevent) object as its sole argument.

## Example

This example uses [`onblur`](onblur) and `onfocus` to change the text within an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element.

### HTML

    <input type="text" value="CLICK HERE">

### JavaScript

    let input = document.querySelector('input');

    input.onblur = inputBlur;
    input.onfocus = inputFocus;

    function inputBlur() {
      input.value = 'Focus has been lost';
    }

    function inputFocus() {
      input.value = 'Focus is here';
    }

### Result

Try clicking in and out of the form field, and watch its contents change accordingly.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onfocus">HTML Living Standard<br />
<span class="small">The definition of 'onfocus' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onfocus`

1

12

9

9

≤12.1

1

1

18

9

≤12.1

1

1.0

In contrast to IE, in which almost all kinds of elements receive the `focus` event, almost all kinds of elements on Gecko browsers do NOT work with this event.

## See also

- `focus` event
- Related event handler: [`GlobalEventHandlers.onblur`](onblur)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onfocus" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onfocus</a>
