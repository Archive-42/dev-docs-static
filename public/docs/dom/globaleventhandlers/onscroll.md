# GlobalEventHandlers.onscroll

The `onscroll` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `scroll` events.

The `scroll` event fires when the document view or an element has been scrolled, whether by the user, a [Web API](../index), or the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

**Note:** Don't confuse `onscroll` with [`onwheel`](onwheel)!

`onwheel` handles general wheel rotation, while `onscroll` handles scrolling of an object's content.

## Syntax

    target.onscroll = functionRef

### Value

`functionRef`  
A function name, or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`UIEvent`](../uievent) object as its sole argument.

Only one `onscroll` handler can be assigned to an object at a time.

For greater flexibility, you can pass a `scroll` event to the [`EventTarget.addEventListener()`](../eventtarget/addeventlistener) method instead.

## Example

This example monitors scrolling on a [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea), and logs the element's vertical scroll position accordingly.

### HTML

    <textarea>1 2 3 4 5 6 7 8 9</textarea>
    <p id="log"></p>

### CSS

    textarea {
      width: 4rem;
      height: 8rem;
      font-size: 3rem;
    }

### JavaScript

    const textarea = document.querySelector('textarea');
    const log = document.getElementById('log');

    textarea.onscroll = logScroll;

    function logScroll(e) {
      log.textContent = `Scroll position: ${e.target.scrollTop}`;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-onscroll">HTML Living Standard<br />
<span class="small">The definition of 'onscroll' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-scroll">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'onscroll' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`onscroll`

1

12

9

9

≤12.1

1.3

1

18

9

≤12.1

1

1.0

## See also

- [Document: `scroll` event](../document/scroll_event)
- [Element: `scroll` event](../element/scroll_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onscroll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onscroll</a>
