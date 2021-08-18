HTMLElement.focus()
===================

The `HTMLElement.focus()` method sets focus on the specified element, if it can be focused. The focused element is the element which will receive keyboard and similar events by default.

Syntax
------

    element.focus(options); // Object parameter

### Parameters

 `options` <span class="badge inline optional">Optional</span>   
An optional object providing options to control aspects of the focusing process. This object may contain the following property:

 `preventScroll` <span class="badge inline optional">Optional</span>   
A Boolean value indicating whether or not the browser should scroll the document to bring the newly-focused element into view. A value of `false` for `preventScroll` (the default) means that the browser will scroll the element into view after focusing it. If `preventScroll` is set to `true`, no scrolling will occur.

Examples
--------

### Focus on a text field

#### JavaScript

    focusMethod = function getFocus() {
      document.getElementById("myTextField").focus();
    }

#### HTML

    <input type="text" id="myTextField" value="Text field.">
    <p></p>
    <button type="button" onclick="focusMethod()">Click me to focus on the text field!</button>

#### Result

### Focus on a button

#### JavaScript

    focusMethod = function getFocus() {
      document.getElementById("myButton").focus();
    }

#### HTML

    <button type="button" id="myButton">Click Me!</button>
    <p></p>
    <button type="button" onclick="focusMethod()">Click me to focus on the button!</button>

#### Result

### Focus with focusOption

#### JavaScript

    focusScrollMethod = function getFocus() {
      document.getElementById("myButton").focus({preventScroll:false});
    }
    focusNoScrollMethod = function getFocusWithoutScrolling() {
      document.getElementById("myButton").focus({preventScroll:true});
    }

#### HTML

    <button type="button" onclick="focusScrollMethod()">Click me to focus on the button!</button>
    <button type="button" onclick="focusNoScrollMethod()">Click me to focus on the button without scrolling!</button>

    <div id="container" style="height: 1000px; width: 1000px;">
    <button type="button" id="myButton" style="margin-top: 500px;">Click Me!</button>
    </div>

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/editing.html#dom-focus">HTML Living Standard<br />
<span class="small">The definition of 'focus' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#focus()-0">HTML 5.1<br />
<span class="small">The definition of 'focus' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/editing.html#dom-focus">HTML5<br />
<span class="small">The definition of 'focus' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-32130014">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'focus' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#method-focus">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'focus' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr></tbody></table>

Notes
-----

-   If you call `HTMLElement.focus()` from a mousedown event handler, you must call `event.preventDefault()` to keep the focus from leaving the `HTMLElement`
-   Behavior of the focus in relation to different HTML features like [`tabindex`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-tabindex) or [shadow dom](https://developer.mozilla.org/en-US/docs/Glossary/Shadow_tree), which previously remained under-specified, were recently updated (as October of 2019). Checkout [WHATWG blog](https://blog.whatwg.org/focusing-on-focus) for more info.

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

`focus`

1

12

1.5

5.5

8

3

4.4

18

4

10.1

1

1.0

`preventScroll_option`

64

≤79

68

?

51

No

64

64

68

47

No

9.0

See also
--------

-   DOM method [`HTMLOrForeignElement.blur`](blur) to remove the focus from an element.
-   [`document.activeElement`](../document/activeelement) to know which is the currently focused element.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/focus" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/focus</a>
