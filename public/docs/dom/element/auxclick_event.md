# Element: auxclick event

The `auxclick` event is fired at an [`Element`](../element) when a non-primary pointing device button (any mouse button other than the primary—usually leftmost—button) has been pressed and released both within the same element.

`auxclick` is fired after the `mousedown` and `mouseup` events have been fired, in that order.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../mouseevent"><code>MouseEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onauxclick"><code>onauxclick</code></a></td></tr></tbody></table>

## Preventing default actions

For the vast majority of browsers that map middle click to opening a link in a new tab, including Firefox, it is possible to cancel this behavior by calling [`preventDefault()`](../event/preventdefault) from within an `auxclick` event handler.

When listening for `auxclick` events originating on elements that do not support input or navigation, you will often want to explicitly prevent other default actions mapped to the down action of the middle mouse button. On Windows this is usually autoscroll, and on macOS and Linux this is usually clipboard paste. This can be done by preventing the default behavior of the `mousedown` or `pointerdown` event.

Additionally, you may need to avoid opening a system context menu after a right click. Due to timing differences between operating systems, this too is not a preventable default behavior of `auxclick`. Instead, this can be done by preventing the default behavior of the `contextmenu` event.

## Examples

In this example we define functions for two event handlers — [`onclick`](../globaleventhandlers/onclick) and [`onauxclick`](../globaleventhandlers/onauxclick). The former changes the color of the button background, while the latter changes the button foreground (text) color. You also can see the two functions in action by trying the demo out with a multi-button mouse ([see it live on GitHub](https://mdn.github.io/dom-examples/auxclick/); also [see the source code](https://github.com/mdn/dom-examples/blob/master/auxclick/index.html)).

### JavaScript

    let button = document.querySelector('button');
    let html = document.querySelector('html');

    function random(number) {
      return Math.floor(Math.random() * number);
    }

    function randomColor() {
        return `rgb(${random(255)}, ${random(255)}, ${random(255)})`;
    }

    button.onclick = function() {
      button.style.backgroundColor = randomColor();
    };

    button.onauxclick = function(e) {
      e.preventDefault();
      button.style.color = randomColor();
    }

    button.oncontextmenu = function(e) {
      e.preventDefault();
    }

Notice that in addition to capturing the `auxclick` event using [`onauxclick`](../globaleventhandlers/onauxclick), the [`contextmenu`](contextmenu_event) event is also captured, and [`preventDefault()`](../event/preventdefault) called on that event, in order to prevent the context menu from popping up after the color change is applied.

### HTML

    <button><h1>Click me!</h1></button>

**Note**: If you are using a three-button mouse, you'll notice that the `onauxclick` handler is run when any of the non-left mouse buttons are clicked (usually including any "special" buttons on gaming mice).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-auxclick">UI Events<br />
<span class="small">The definition of 'auxclick' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`auxclick_event`

55

≤79

53

Starting in Firefox 68, the `auxclick` event is used to trigger the _new tab on middle-click_ action; previously, this had been done with the `click` event. Apps can prevent middle-click from opening new tabs (or middle-click to paste, if that feature is enabled) by intercepting `auxclick` on links, and `auxclick` event handlers can now open popups without triggering the popup blocker.

No

42

No

55

55

53

42

No

6.0

## See also

- [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
- `click`
- `contextmenu`
- `dblclick`
- `mousedown`
- `mouseup`
- `pointerdown`
- `pointerup`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/auxclick_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/auxclick_event</a>
