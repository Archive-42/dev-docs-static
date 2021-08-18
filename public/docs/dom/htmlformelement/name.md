HTMLFormElement.name
====================

The `HTMLFormElement.name` property represents the name of the current [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element as a string.

If your [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element contains an element named *name* then that element overrides the `form.name` property, so that you can't access it. Internet Explorer (IE) does not allow the name attribute of an element created using `createElement()` to be set or modified using the `name` property.

Syntax
------

    var string = form.name;
    form.name = string;

Example
-------

    var form1name = document.getElementById('form1').name;

    if (form1name != document.form.form1) {
      // Browser doesn't support this form of reference
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-form-name">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFormElement: name' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`name`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/name</a>
