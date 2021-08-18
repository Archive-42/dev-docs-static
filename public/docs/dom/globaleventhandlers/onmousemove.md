GlobalEventHandlers.onmousemove
===============================

The `onmousemove` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `mousemove` events.

The `mousemove` event fires when the user moves the mouse.

Syntax
------

    target.onmousemove = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`MouseEvent`](../mouseevent) object as its sole argument.

Examples
--------

### Tooltips

This example creates link tooltips that follow your mouse. It uses the `onmousemove`, [`onmouseover`](onmouseover), and [`onmouseout`](onmouseout) event handlers.

#### HTML

    <p><a href="#" data-tooltip="First link">See a tooltip here &hellip;</a></p>
    <p><a href="#" data-tooltip="Second link">&hellip; or here!</a></p>

#### CSS

    .tooltip {
      position: absolute;
      z-index: 9999;
      padding: 6px;
      background: #ffd;
      border: 1px #886 solid;
      border-radius: 5px;
    }

#### JavaScript

    const tooltip = new (function() {
      const node = document.createElement('div');
      node.className = 'tooltip';
      node.setAttribute('hidden', '');
      document.body.appendChild(node);

      this.follow = function(event) {
        node.style.left = event.clientX + 20 + 'px';
        node.style.top = event.clientY + 10 + 'px';
      };

      this.show = function(event) {
        node.textContent = event.target.dataset.tooltip;
        node.removeAttribute('hidden');
      };

      this.hide = function() {
        node.setAttribute('hidden', '');
      };
    })();

    const links = document.querySelectorAll('a');

    links.forEach(link => {
      link.onmouseover = tooltip.show;
      link.onmousemove = tooltip.follow;
      link.onmouseout = tooltip.hide;
    });

#### Result

### Draggable elements

We also have an example available showing the use of the `onmousemove` event handler with draggable objects — [view the example in action](https://mdn.mozillademos.org/files/5031/draggable_elements.html).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onmousemove">HTML Living Standard<br />
<span class="small">The definition of 'onmousemove' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onmousemove`

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

-   `mousemove` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousemove" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousemove</a>
