# GlobalEventHandlers.oncancel

The `oncancel` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `cancel` events sent to a [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) element.

The `cancel` event fires when the user indicates a wish to dismiss a `<dialog>`. This event handler prevents the event from bubbling, so any parent handlers are not notified of the event.

## Syntax

    target.oncancel = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives an [`Event`](../event) object as its sole argument.

Only one `oncancel` handler can be assigned to an object at a time. You may prefer to use the [`EventTarget.addEventListener()`](../eventtarget/addeventlistener) method instead, since it's more flexible.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-oncancel">HTML Living Standard<br />
<span class="small">The definition of 'oncancel' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`oncancel`

32

79

No

No

19

No

4.4.3

32

No

19

No

2.0

## See also

- `cancel` event
- HTML [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) element
- Related event handler: [`GlobalEventHandlers.onclose`](onclose)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncancel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncancel</a>
