HTMLLabelElement.form
=====================

The read-only `HTMLLabelElement.form` property returns an [`HTMLFormElement`](../htmlformelement) object which represents the form of which the label's associated control is a part, or null if there is either no associated control, or if that control isn't in a form.

This property is just a shortcut for `HTMLLabelElement.control.form`.

Syntax
------

    form = HTMLLabelElement.form

### Value

An [`HTMLFormElement`](../htmlformelement) which represents the form with which the label's [`control`](control) is associated. If [`control`](control) is `null` (meaning the label isn't associated with a control), or if the control isn't part of a form, this property returns `null`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#dom-label-form">HTML Living Standard<br />
<span class="small">The definition of 'form' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`form`

1

12

1

6

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

-   [`HTMLLabelElement`](../htmllabelelement)
-   [`HTMLElement`](../htmlelement)
-   [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)
-   [HTML forms guide](https://developer.mozilla.org/en-US/docs/Learn/Forms)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement/form" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement/form</a>
