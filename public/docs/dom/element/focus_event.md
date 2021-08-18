# Element: focus event

The `focus` event fires when an element has received focus. The main difference between this event and [`focusin`](focusin_event) is that `focusin` bubbles while `focus` does not.

The opposite of `focus` is [`blur`](blur_event).

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../focusevent"><code>FocusEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onfocus"><code>onfocus</code></a></td></tr><tr class="odd"><td>Sync / Async</td><td>Sync</td></tr><tr class="even"><td>Composed</td><td>Yes</td></tr></tbody></table>

## Examples

### Simple example

#### HTML

    <form id="form">
      <input type="text" placeholder="text input">
      <input type="password" placeholder="password">
    </form>

#### JavaScript

    const password = document.querySelector('input[type="password"]');

    password.addEventListener('focus', (event) => {
      event.target.style.background = 'pink';
    });

    password.addEventListener('blur', (event) => {
      event.target.style.background = '';
    });

#### Result

### Event delegation

There are two ways of implementing event delegation for this event: by using the `focusin` event, or by setting the `useCapture` parameter of [`addEventListener()`](../eventtarget/addeventlistener) to `true`.

#### HTML

    <form id="form">
      <input type="text" placeholder="text input">
      <input type="password" placeholder="password">
    </form>

#### JavaScript

    const form = document.getElementById('form');

    form.addEventListener('focus', (event) => {
      event.target.style.background = 'pink';
    }, true);

    form.addEventListener('blur', (event) => {
      event.target.style.background = '';
    }, true);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-focus">UI Events</a></td><td><span class="spec-wd">Working Draft</span></td><td>Added info that this event is composed.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-focus">Document Object Model (DOM) Level 3 Events Specification</a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`focus_event`

1

12

24

6-24

The interface for this event is [`Event`](https://developer.mozilla.org/docs/Web/API/Event), not [`FocusEvent`](https://developer.mozilla.org/docs/Web/API/FocusEvent).

9

11.6

3.1

1

18

24

6-24

The interface for this event is [`Event`](https://developer.mozilla.org/docs/Web/API/Event), not [`FocusEvent`](https://developer.mozilla.org/docs/Web/API/FocusEvent).

12.1

2

1.0

## See also

- Related events: [`blur`](blur_event), [`focusin`](focusin_event), [`focusout`](focusout_event)
- This event on `Window` targets: [`focus`](../window/focus_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/focus_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/focus_event</a>
