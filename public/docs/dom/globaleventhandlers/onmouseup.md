GlobalEventHandlers.onmouseup
=============================

The `onmouseup` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `mouseup` events.

The `mouseup` event fires when the user releases the mouse button.

**Note:** The opposite of `onmouseup` is [`onmousedown`](onmousedown).

Syntax
------

    target.onmouseup = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`MouseEvent`](../mouseevent) object as its sole argument.

Example
-------

In this example, a piece of "toast" hides when you click down with the mouse, and reappears when you release. It uses the [`onmousedown`](onmousedown) and `onmouseup` event handlers.

### HTML

    <div class="container">
      <div class="toaster"></div>
      <div class="toast">Hello world!</div>
    </div>

### CSS

    .container {
      position: absolute;
      left: 50%;
      bottom: 20px;
      transform: translate(-50%);
    }

    .toaster {
      width: 160px;
      height: 110px;
      background: #bbb;
      border-radius: 10px 10px 0 0;
    }

    .toast {
      position: absolute;
      left: 50%;
      top: 50%;
      z-index: -1;
      width: 100px;
      height: 50px;
      padding: 10px;
      background: #ed9;
      border-radius: 10px 10px 0 0;
      transform: translate(-50%, -90px);
      transition: transform .3s;
    }

    .depressed {
      transform: translate(-50%, -50%);
    }

### JavaScript

    function depress() {
      toast.classList.add('depressed');
    }

    function release() {
      toast.classList.remove('depressed');
    }

    const toaster = document.querySelector('.toaster');
    const toast = document.querySelector('.toast');

    toaster.onmousedown = depress;
    document.onmouseup = release;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onmouseup">HTML Living Standard<br />
<span class="small">The definition of 'onmouseup' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onmouseup`

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

See also
--------

-   `mouseup` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseup" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseup</a>
