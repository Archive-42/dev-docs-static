Element: focusout event
=======================

The `focusout` event fires when an element is about to lose focus. The main difference between this event and [`blur`](blur_event) is that `focusout` [bubbles](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#event_bubbling_and_capture) while `blur` does not.

The opposite of `focusout` is [`focusin`](focusin_event).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../focusevent"><code>FocusEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>onfocusout</code></span></td></tr><tr class="odd"><td>Sync / Async</td><td>Sync</td></tr><tr class="even"><td>Composed</td><td>Yes</td></tr></tbody></table>

Examples
--------

### Live example

#### HTML

    <form id="form">
      <input type="text" placeholder="text input">
      <input type="password" placeholder="password">
    </form>

#### JavaScript

    const form = document.getElementById('form');

    form.addEventListener('focusin', (event) => {
      event.target.style.background = 'pink';
    });

    form.addEventListener('focusout', (event) => {
      event.target.style.background = '';
    });

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-focusout">UI Events</a></td><td><span class="spec-wd">Working Draft</span></td><td>Added info that this event is composed.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-focusout">Document Object Model (DOM) Level 3 Events Specification</a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`focusout_event`

1

12

52

9

11.6

5

1

18

52

12.1

4.2

1.0

See also
--------

-   Related events: [`blur`](blur_event), [`focus`](focus_event), [`focusin`](focusin_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/focusout_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/focusout_event</a>
