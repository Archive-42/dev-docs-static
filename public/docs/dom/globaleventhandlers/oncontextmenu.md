GlobalEventHandlers.oncontextmenu
=================================

The `oncontextmenu` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `contextmenu` events.

The `contextmenu` event typically fires when the right mouse button is clicked on the window. Unless the default behavior is prevented, the browser context menu will activate.

Syntax
------

    target.oncontextmenu = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives an [`Event`](../event) object as its sole argument.

Only one `oncontextmenu` handler can be assigned to an object at a time. You may prefer to use the [`EventTarget.addEventListener()`](../eventtarget/addeventlistener) method instead, since it's more flexible.

Examples
--------

### Disabling context menus

This snippet prevents context menus from opening in the window. The context menu typically appears upon a right click.

#### HTML

    <p>Try opening the context menu. Is it disabled?<p>

#### JavaScript

    window.oncontextmenu = (e) => {
      e.preventDefault();
    }

#### Result

### Pausing an animation

This example pauses a spinning shape whenever you open the context menu.

#### HTML

    <div class="shape">Spinning</div>
    <p class="note" hidden>Click to unpause.</p>

#### CSS

    @keyframes spin {
      from {
        transform: rotate(0);
      }
      to {
        transform: rotate(1turn);
      }
    }

    .shape {
      width: 8em;
      height: 8em;
      display: flex;
      align-items: center;
      justify-content: center;
      animation: spin 18s linear infinite;
      background: lightsalmon;
      border-radius: 42%;
      margin: 1em;
    }

    .paused {
      background-color: #ddd;
    }

    .paused .shape {
      animation-play-state: paused;
    }

#### JavaScript

    function pause(e) {
      body.classList.add('paused');
      note.removeAttribute('hidden');
    }

    function play(e) {
      body.classList.remove('paused');
      note.setAttribute('hidden', '');
    }

    const body = document.querySelector('body');
    const note = document.querySelector('.note');

    window.oncontextmenu = pause;
    window.onpointerdown = play;

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-oncontextmenu">HTML Living Standard<br />
<span class="small">The definition of 'oncontextmenu' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`oncontextmenu`

1

12

9

5

≤12.1

4

1

18

9

≤12.1

3.2

1.0

Unless the default behavior is prevented, the browser context menu will activate upon right-click. However, IE8 has a bug with this and will not activate the context menu if a `contextmenu` event handler is defined.

See also
--------

-   `contextmenu` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncontextmenu" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncontextmenu</a>
