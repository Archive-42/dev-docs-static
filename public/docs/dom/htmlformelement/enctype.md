HTMLFormElement.enctype
=======================

The `HTMLFormElement.enctype` property is the [MIME type](https://en.wikipedia.org/wiki/Mime_type) of content that is used to submit the form to the server. Possible values are:

-   `application/x-www-form-urlencoded`: The initial default type.
-   `multipart/form-data`: The type that allows file [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element(s) to upload file data.
-   `text/plain`: A type introduced in HTML5.

This value can be overridden by a [`formenctype`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button#attr-formenctype) attribute on a [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) or [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element.

Syntax
------

    var string = form.enctype;
    form.enctype = string;

Example
-------

    form.enctype = 'application/x-www-form-urlencoded';

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-fs-enctype">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFormElement: enctype' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`enctype`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/enctype" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/enctype</a>
