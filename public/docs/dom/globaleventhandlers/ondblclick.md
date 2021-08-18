# GlobalEventHandlers.ondblclick

The `ondblclick` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `dblclick` events on the given element.

The `dblclick` event is raised when the user double clicks an element. It fires after two `click` events.

## Syntax

    target.ondblclick = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`MouseEvent`](../mouseevent) object as its sole argument. Within the function, `this` will be the element upon which the event was triggered.

Only one `ondblclick` handler can be assigned to an object at a time. You may prefer to use the [`EventTarget.addEventListener()`](../eventtarget/addeventlistener) method instead, since it's more flexible.

## Example

This example logs the position of double clicks.

### HTML

    <p>Double click anywhere in this example.</p>
    <p id="log"></p>

### JavaScript

    let log = document.getElementById('log');

    document.ondblclick = logDoubleClick;

    function logDoubleClick(e) {
      log.textContent = `Position: (${e.clientX}, ${e.clientY})`;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-ondblclick">HTML Living Standard<br />
<span class="small">The definition of 'ondblclick' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`ondblclick`

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

- `dblclick` event
- Related event handlers
  - [`GlobalEventHandlers.onauxclick`](onauxclick)
  - [`GlobalEventHandlers.onclick`](onclick)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondblclick" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondblclick</a>
