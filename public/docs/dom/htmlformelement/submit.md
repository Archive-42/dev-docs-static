HTMLFormElement.submit()
========================

The `HTMLFormElement.submit()` method submits a given [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form).

This method is similar, but not identical to, activating a form's submit [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button). When invoking this method directly, however:

-   No `submit` event is raised. In particular, the form's [`onsubmit`](../globaleventhandlers/onsubmit) event handler is not run.
-   [Constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) is not triggered.

The [`HTMLFormElement.requestSubmit()`](requestsubmit) method is identical to activating a form's submit [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) and does not have these differences.

If a form control (such as a submit button) has a `name` or `id` of `submit`, this method will mask the form's submit method.

[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) with attribute type="submit" will not be submitted with the form when using `HTMLFormElement.submit()`, but it would be submitted when you do it with original HTML form submit.

Syntax
------

    HTMLFormElement.submit()

Example
-------

    document.forms["myform"].submit();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-form-submit">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFormElement: submit' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`submit`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/submit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/submit</a>
