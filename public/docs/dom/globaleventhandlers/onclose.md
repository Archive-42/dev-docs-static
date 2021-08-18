# GlobalEventHandlers.onclose

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `onclose` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `close` events sent to a [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) element.

The `close` event fires when the user closes a `<dialog>`.

**Note:** To handle the closing of a window, use [`onbeforeunload`](../windoweventhandlers/onbeforeunload) or [`onunload`](../windoweventhandlers/onunload).

## Syntax

    target.onclose = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives an [`Event`](../event) object as its sole argument.

Only one `onclose` handler can be assigned to an object at a time. You may prefer to use the [`EventTarget.addEventListener()`](../eventtarget/addeventlistener) method instead, since it's more flexible.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onclose">HTML Living Standard<br />
<span class="small">The definition of 'onclose' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onclose`

32

79

53

No

19

No

4.4.3

32

53

19

No

2.0

## See also

- `close` event
- HTML [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) element
- Related event handler: [`GlobalEventHandlers.oncancel`](oncancel)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclose" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclose</a>
