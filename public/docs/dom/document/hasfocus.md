# Document.hasFocus()

The `hasFocus()` method of the [`Document`](../document) interface returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating whether the document or any element inside the document has focus. This method can be used to determine whether the active element in a document has focus.

When viewing a document, an element with focus is always the [active element](activeelement) in the document, but an active element does not necessarily have focus. For example, an active element within a popup window that is not the foreground doesn't have focus.

## Syntax

    var focused = document.hasFocus();

### Return value

`false` if the active element in the document has no focus; `true` if the active element in the document has focus.

## Example

This example checks whether the document has focus every 300 milliseconds. To test the functionality of `hasFocus()`, click on the button to open a new window, and try switching between the two pages.

### HTML

    <p id="log">Awaiting focus check.</p>
    <button onclick="openWindow()">Open a new window</button>

### JavaScript

    function checkPageFocus() {
      let body = document.querySelector('body');
      let log = document.getElementById('log');

      if (document.hasFocus()) {
        log.textContent = 'This document has the focus.';
        body.style.background = '#fff';
      }
      else {
        log.textContent = 'This document does not have the focus.';
        body.style.background = '#ccc';
      }
    }

    function openWindow() {
      window.open('https://developer.mozilla.org/', 'MDN', 'width=640,height=320,left=150,top=150');
    }

    // Check page focus every 300 milliseconds
    setInterval(checkPageFocus, 300);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-document-hasfocus">HTML Living Standard<br />
<span class="small">The definition of 'Document.hasFocus()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`hasFocus`

1

12

3

5.5

15

4

1

18

4

14

3.2

1.0

## See also

- [Using the Page Visibility API](../page_visibility_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/hasFocus" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/hasFocus</a>
