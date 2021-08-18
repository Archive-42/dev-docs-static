# GlobalEventHandlers.onresize

The `onresize` property of the [`GlobalEventHandlers`](../globaleventhandlers) interface is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `resize` events.

The `resize` event fires after the window has been resized.

## Syntax

    window.onresize = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`FocusEvent`](../focusevent) object as its sole argument.

## Examples

### Window size logger

    <p>Resize the browser window to fire the <code>resize</code> event.</p>
    <p>Window height: <span id="height"></span></p>
    <p>Window width: <span id="width"></span></p>

    const heightOutput = document.querySelector('#height');
    const widthOutput = document.querySelector('#width');

    function resize() {
      heightOutput.textContent = window.innerHeight;
      widthOutput.textContent = window.innerWidth;
    }

    window.onresize = resize;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onresize">HTML Living Standard<br />
<span class="small">The definition of 'onresize' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onresize`

34

79

12-79

In EdgeHTML versions of Edge, this handler was only supported on the [`Window`](https://developer.mozilla.org/docs/Web/API/Window) API.

38

4

In Internet Explorer, this handler was only supported on the [`Window`](https://developer.mozilla.org/docs/Web/API/Window) API.

21

10.1

37

34

38

21

10.3

2.0

## See also

- [Window: `resize` event](../window/resize_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onresize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onresize</a>
