GlobalEventHandlers.onwheel
===========================

The `onwheel` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `wheel` events.

The `wheel` event fires when the user rotates the mouse (or other pointing device) wheel.

**Note:** Don't confuse `onwheel` with [`onscroll`](onscroll): `onwheel` handles general wheel rotation, while `onscroll` handles scrolling of an object's content.

Syntax
------

    target.onwheel = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`WheelEvent`](../wheelevent) object as its sole argument.

Examples
--------

This example shows how to scale an element using the mouse (or other pointing device) wheel.

### HTML

    <div>Scale me with your mouse wheel.</div>

### CSS

    body {
      min-height: 100vh;
      margin: 0;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    div {
      width: 80px;
      height: 80px;
      background: #cdf;
      padding: 5px;
      transition: transform .3s;
    }

### JavaScript

    function zoom(event) {
      event.preventDefault();

      if (event.deltaY < 0) {
        // Zoom in
        scale *= event.deltaY * -2;
      }
      else {
        // Zoom out
        scale /= event.deltaY * 2;
      }

      // Restrict scale
      scale = Math.min(Math.max(.125, scale), 4);

      // Apply scale transform
      el.style.transform = `scale(${scale})`;
    }

    let scale = 1;
    const el = document.querySelector('div');
    document.onwheel = zoom;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onwheel">HTML Living Standard<br />
<span class="small">The definition of 'onwheel' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onwheel`

31

12

17

No

18

7

4.4.3

31

17

18

7

2.0

See also
--------

-   [Document: `wheel` event](../document/wheel_event)
-   [Element: `wheel` event](../element/wheel_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onwheel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onwheel</a>
