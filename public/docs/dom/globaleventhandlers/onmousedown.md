# GlobalEventHandlers.onmousedown

The `onmousedown` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `mousedown` events.

The `mousedown` event fires when the user depresses the mouse button.

**Note:** The opposite of `onmousedown` is [`onmouseup`](onmouseup).

## Syntax

    target.onmousedown = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`MouseEvent`](../mouseevent) object as its sole argument.

## Example

This example reveals part of an image when you press and hold a mouse button. It uses the `onmousedown`, [`onmouseup`](onmouseup), and [`onmousemove`](onmousemove) event handlers.

### HTML

    <div class="container">
      <div class="view" hidden></div>
      <img src="https://interactive-examples.mdn.mozilla.net/media/examples/gecko-320-213.jpg">
    </div>

### CSS

    .container {
      width: 320px;
      height: 213px;
      background: black;
    }

    .view {
      position: absolute;
      width: 100px;
      height: 100px;
      background: white;
      border-radius: 50%;
    }

    img {
      mix-blend-mode: darken;
    }

### JavaScript

    function showView(event) {
      view.removeAttribute('hidden');
      view.style.left = event.clientX - 50 + 'px';
      view.style.top = event.clientY - 50 + 'px';
      event.preventDefault();
    }

    function moveView(event) {
      view.style.left = event.clientX - 50 + 'px';
      view.style.top = event.clientY - 50 + 'px';
    }

    function hideView(event) {
      view.setAttribute('hidden', '');
    }

    const container = document.querySelector('.container');
    const view = document.querySelector('.view');

    container.onmousedown = showView;
    container.onmousemove = moveView;
    document.onmouseup = hideView;

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onmousedown">HTML Living Standard<br />
<span class="small">The definition of 'onmousedown' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onmousedown`

1

12

9

4

≤12.1

1

1

18

9

≤12.1

1

1.0

## See also

- `mousedown` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousedown" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousedown</a>
