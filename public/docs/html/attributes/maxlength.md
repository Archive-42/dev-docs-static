HTML attribute: maxlength
=========================

**Draft**

This page is not complete.

The `maxlength` attribute defines the maximum number of characters (as UTF-16 code units) the user can enter into an [`<input>`](../element/input) or [`<textarea>`](../element/textarea). This must be an integer value 0 or higher. If no maxlength is specified, or an invalid value is specified, the input or textarea has no maximum length.

Any `maxlength` value must be greater than or equal to the value of `minlength`, if present and valid. The input will fail constraint validation if the length of the text value of the field is greater than maxlength UTF-16 code units long. Constraint validation is only applied when the value is changed by the user.

### Constraint validation

While the browser will generally prevent user from entering more text than the maxlength attribute allows, should the length be longer than the maxlength allows, the read-only [`tooLong`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooLong) property of a [`ValidityState`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState) object will be true.

Examples
--------

    <input type="password" maxlength="4"/>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/input.html#attr-input-maxlength">HTML Living Standard<br />
<span class="small">The definition of 'maxlength attribute' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/input.html#attr-maxlength-accept">HTML 5.1<br />
<span class="small">The definition of 'maxlength attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `html.elements.attribute.maxlength`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`minlength`](minlength)
-   [`size`](size)
-   [`pattern`](pattern)
-   [Constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation)
-   [Constraint validation API](https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation)
-   [`<input>`](../element/input)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/maxlength" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/maxlength</a>
