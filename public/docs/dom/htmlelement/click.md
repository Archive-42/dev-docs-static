# HTMLElement.click()

The `HTMLElement.click()` method simulates a mouse click on an element.

When `click()` is used with supported elements (such as an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)), it fires the element's click event. This event then bubbles up to elements higher in the document tree (or event chain) and fires their click events.

## Syntax

    element.click()

## Example

Simulate a mouse-click when moving the mouse pointer over a checkbox:

### HTML

    <form>
      <input type="checkbox" id="myCheck" onmouseover="myFunction()" onclick="alert('click event occurred')">
    </form>

### JavaScript

    // On mouse-over, execute myFunction
    function myFunction() {
      document.getElementById("myCheck").click();
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-click">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-2651361">Document Object Model (DOM) Level 2 HTML Specification</a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`click`

9

Before Chrome 19, `click()` is only defined on buttons and inputs.

12

3

\["Before Firefox 5, `click()` is only defined on buttons and inputs, and has no effect on text and file inputs.", "Starting in Firefox 75, the `click()` function works even when the element is not attached to a DOM tree."\]

5.5

10.5

6

≤37

Before Android WebView 4.4, `click()` is only defined on buttons and inputs.

18

Before Chrome 19, `click()` is only defined on buttons and inputs.

4

\["Before Firefox 5, `click()` is only defined on buttons and inputs, and has no effect on text and file inputs.", "Starting in Firefox for Android 79, the `click()` function works even when the element is not attached to a DOM tree."\]

11

6

1.0

Before Samsung Internet 1.5, `click()` is only defined on buttons and inputs.

## See also

- Related event handlers
  - [`GlobalEventHandlers.onclick`](../globaleventhandlers/onclick)
  - [`GlobalEventHandlers.ondblclick`](../globaleventhandlers/ondblclick)
  - [`GlobalEventHandlers.onauxclick`](../globaleventhandlers/onauxclick)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/click" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/click</a>
