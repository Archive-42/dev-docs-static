# Event.defaultPrevented

The `defaultPrevented` read-only property of the [`Event`](../event) interface returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether or not the call to [`Event.preventDefault()`](preventdefault) canceled the event.

**Note:** You should use this instead of the non-standard, deprecated `getPreventDefault()` method (see [bug 691151](https://bugzilla.mozilla.org/show_bug.cgi?id=691151)).

## Syntax

    var defaultWasPrevented = event.defaultPrevented;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), where `true` indicates that the default [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) action was prevented, and `false` indicates that it was not.

## Example

This example logs attempts to visit links from two [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) elements. JavaScript is used to prevent the second link from working.

### HTML

    <p><a id="link1" href="#link1">Visit link 1</a></p>
    <p><a id="link2" href="#link2">Try to visit link 2</a> (you can't)</p>
    <p id="log"></p>

### JavaScript

    function stopLink(event) {
      event.preventDefault();
    }

    function logClick(event) {
      const log = document.getElementById('log');

      if (event.target.tagName === 'A') {
        if (event.defaultPrevented) {
          log.innerText = 'Sorry, but you cannot visit this link!\n' + log.innerText;
        }
        else {
          log.innerText = 'Visiting link...\n' + log.innerText;
        }
      }
    }

    const a = document.getElementById('link2');
    a.addEventListener('click', stopLink);
    document.addEventListener('click', logClick);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-defaultprevented">DOM<br />
<span class="small">The definition of 'Event.defaultPrevented()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`defaultPrevented`

18

12

6

9

11

5

≤37

18

6

11

5

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/defaultPrevented" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/defaultPrevented</a>
