GlobalEventHandlers.onblur
==========================

The `onblur` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `blur` events. It's available on [`Element`](../element), [`Document`](../document), and [`Window`](../window).

The `blur` event is raised when an element loses focus.

**Note:** The opposite of `onblur` is [`onfocus`](onfocus).

Syntax
------

    target.onblur = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`FocusEvent`](../focusevent) object as its sole argument.

Example
-------

This example uses `onblur` and [`onfocus`](onfocus) to change the text within an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element.

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onblur">HTML Living Standard<br />
<span class="small">The definition of 'onblur' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onblur`

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

In contrast to IE, in which almost all kinds of elements receive the `blur` event, only a few kinds of elements on Gecko browsers work with this event.

See also
--------

-   `blur` event
-   Related event handler: [`GlobalEventHandlers.onfocus`](onfocus)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onblur" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onblur</a>
