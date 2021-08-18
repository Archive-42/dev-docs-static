Window: blur event
==================

The `blur` event fires when an element has lost focus.

The opposite of `blur` is [`focus`](focus_event).

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../focusevent"><code>FocusEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onblur"><code>onblur</code></a></td></tr><tr class="odd"><td>Sync / Async</td><td>Sync</td></tr><tr class="even"><td>Composed</td><td>Yes</td></tr></tbody></table>

Examples
--------

### Live example

This example changes the appearance of a document when it loses focus. It uses [`addEventListener()`](../eventtarget/addeventlistener) to monitor [`focus`](focus_event) and `blur` events.

#### HTML

    <p id="log">Click on this document to give it focus.</p>

#### CSS

    .paused {
      background: #ddd;
      color: #555;
    }

#### JavaScript

    function pause() {
      document.body.classList.add('paused');
      log.textContent = 'FOCUS LOST!';
    }

    function play() {
      document.body.classList.remove('paused');
      log.textContent = 'This document has focus. Click outside the document to lose focus.';
    }

    const log = document.getElementById('log');

    window.addEventListener('blur', pause);
    window.addEventListener('focus', play);

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-blur">UI Events</a></td><td><span class="spec-wd">Working Draft</span></td><td>Added info that this event is composed.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-blur">Document Object Model (DOM) Level 3 Events Specification</a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`blur_event`

5

12

Yes

Apart from firing the event on `window` as other browsers do, Firefox also fires the event on the `document` object. See [bug 1228802](https://bugzil.la/1228802).

Yes-24

The interface for this event is [`Event`](https://developer.mozilla.org/docs/Web/API/Event), not [`FocusEvent`](https://developer.mozilla.org/docs/Web/API/FocusEvent).

Yes

12.1

5.1

≤37

18

Yes

12.1

5.1

1.0

The value of [`Document.activeElement`](../document/activeelement) varies across browsers while this event is being handled ([bug 452307](https://bugzilla.mozilla.org/show_bug.cgi?id=452307)): IE10 sets it to the element that the focus will move to, while Firefox and Chrome often set it to the `body` of the document.

See also
--------

-   Related event: [`focus`](focus_event)
-   This event on `Element` targets: [`blur`](../element/blur_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/blur_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/blur_event</a>
