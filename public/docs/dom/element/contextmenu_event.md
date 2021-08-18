# Element: contextmenu event

The `contextmenu` event fires when the user attempts to open a context menu. This event is typically triggered by clicking the right mouse button, or by pressing the context menu key. In the latter case, the context menu is displayed at the bottom left of the focused element, unless the element is a tree, in which case the context menu is displayed at the bottom left of the current row.

Any right-click event that is not disabled (by calling the event's [`preventDefault()`](../event/preventdefault) method) will result in a `contextmenu` event being fired at the targeted element.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../mouseevent"><code>MouseEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/oncontextmenu"><code>oncontextmenu</code></a></td></tr></tbody></table>

## Examples

In this example, the default action of the `contextmenu` event is canceled using `preventDefault()` when the `contextmenu` event is fired at the first paragraph. As a result, the first paragraph will do nothing when right-clicked, while the second paragraph will show the standard context menu offered by your browser.

### HTML

    <p id="noContextMenu">The context menu has been disabled on this paragraph.</p>
    <p>But it has not been disabled on this one.</p>

### JavaScript

    const noContext = document.getElementById('noContextMenu');

    noContext.addEventListener('contextmenu', e => {
      e.preventDefault();
    });

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-contextmenu">HTML Living Standard<br />
<span class="small">The definition of 'contextmenu' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`contextmenu_event`

1

12

6

9

10.5

3

1

18

6

11.1

1

1.0

## See also

- [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
- `auxclick`
- `click`
- `dblclick`
- `mousedown`
- `mouseup`
- `pointerdown`
- `pointerup`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/contextmenu_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/contextmenu_event</a>
