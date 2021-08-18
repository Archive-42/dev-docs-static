HTML attribute: for
===================

The `for` attribute is an allowed attribute for [`<label>`](../element/label) and [`<output>`](../element/output). When used on a `<label>` element it indicates the form element that this label describes. When used on an `<output>` element it allows for an explicit relationship between the elements that represent values which are used in the output.

Usage
-----

When used as an attribute of `<label>`, the `for` attribute has a value which is the `id` of the form element it relates to.

    <label for="username">Your name</label>
    <input type="text" id="username">

When used as an attribute of `<output>`, the `for` attribute has a value which is a space separated list of the `id` values of the elements which are used to create the output.

    <input type="range" id="b" name="b" value="50"> +
    <input type="number" id="a" name="a" value="10"> =
    <output name="result" for="a b">60</output>

Examples
--------

See examples of usage on the element pages for [`<label>`](../element/label) and [`<output>`](../element/output).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#attr-label-for">HTML Living Standard<br />
<span class="small">The definition of 'for as used with label' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/form-elements.html#attr-output-for">HTML Living Standard<br />
<span class="small">The definition of 'for as used with output' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#element-attrdef-label-for">HTML5<br />
<span class="small">The definition of 'for as used with label' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#element-attrdef-output-for">HTML5<br />
<span class="small">The definition of 'for as used with output' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`for`

10

≤18

4

No

11

7

Yes

Yes

4

?

Yes

Yes

`form`

10

≤18

4

No

11

7

Yes

Yes

4

?

Yes

Yes

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

`for`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

BCD tables only load in the browser

### Support with output

BCD tables only load in the browser

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/for" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/for</a>
