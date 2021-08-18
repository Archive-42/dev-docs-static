Window.frameElement
===================

The `Window.frameElement` property returns the element (such as [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) or [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object)) in which the window is embedded.

**Note:** Despite this property's name, it works for documents embedded within any embedding point, including [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object), [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), or [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed).

Syntax
------

    const frameEl = window.frameElement

### Value

The element which the window is embedded into. If the window isn't embedded into another document, or if the document into which it's embedded has a different [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin), the value is [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) instead.

Example
-------

    const frameEl = window.frameElement;
    // If we're embedded, change the containing element's URL to 'https://mozilla.org/'
    if (frameEl) {
      frameEl.src = 'https://mozilla.org/';
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#dom-frameelement">HTML Living Standard<br />
<span class="small">The definition of 'Window.frameElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`frameElement`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   [`window.frames`](frames) returns an array-like object, listing the direct sub-frames of the current window.
-   [`window.parent`](parent) returns the parent window, which is the window containing the `frameElement` of the child window.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/frameElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/frameElement</a>
