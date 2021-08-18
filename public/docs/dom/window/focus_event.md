Window: focus event
===================

The `focus` event fires when an element has received focus.

The opposite of `focus` is [`blur`](blur_event).

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../focusevent"><code>FocusEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onfocus"><code>onfocus</code></a></td></tr><tr class="odd"><td>Sync / Async</td><td>Sync</td></tr><tr class="even"><td>Composed</td><td>Yes</td></tr></tbody></table>

Examples
--------

### Live example

This example changes the appearance of a document when it loses focus. It uses [`addEventListener()`](../eventtarget/addeventlistener) to monitor `focus` and [`blur`](blur_event) events.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-focus">UI Events</a></td><td><span class="spec-wd">Working Draft</span></td><td>Added info that this event is composed.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-focus">Document Object Model (DOM) Level 3 Events Specification</a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`focus_event`

Yes

12

Yes

Apart from firing the event on `window` as other browsers do, Firefox also fires the event on the `document` object. See [bug 1228802](https://bugzil.la/1228802).

Yes-24

The interface for this event is [`Event`](https://developer.mozilla.org/docs/Web/API/Event), not [`FocusEvent`](https://developer.mozilla.org/docs/Web/API/FocusEvent).

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   Related event: [`blur`](blur_event)
-   This event on `Element` targets: [`focus`](../element/focus_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/focus_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/focus_event</a>
