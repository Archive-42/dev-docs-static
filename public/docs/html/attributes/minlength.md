HTML attribute: minlength
=========================

The `minlength` attribute defines the minimum number of characters (as UTF-16 code units) the user can enter into an [`<input>`](../element/input) or [`<textarea>`](../element/textarea). This must be an integer value 0 or higher. If no minlength is specified, or an invalid value is specified, the input has no minimum length. This value must be less than or equal to the value of [maxlength](maxlength), otherwise the value will never be valid, as it is impossible to meet both criteria.

The input will fail constraint validation if the length of the text value of the field is less than minlength UTF-16 code units long, with [`validityState.tooShort`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooShort) returning `true`. Constraint validation is only applied when the value is changed by the user. Once submission fails, some browsers will display an error message indicating the minimum length required and the current length.

Examples
--------

By adding `minlength="5"`, the value must either be empty or five characters or longer to be valid.

    <label for="fruit">Enter a fruit name that is at least 5 letters long</label> <input type="text" minlength="5" id="fruit">

We can use pseudoclasses to style the element based on whether the value is valid. The value will be valid as long as it is either null (empty) or five or more characters long. *Lime* is invalid, *lemon is valid*.

    input {
      border: 2px solid currentcolor;
    }
    input:invalid {
      border: 2px dashed red;
    }
    input:invalid:focus {
      background-image: linear-gradient(pink, lightgreen);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/input.html#attr-input-minlength">HTML Living Standard<br />
<span class="small">The definition of 'minlength attribute' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/input.html#attr-minlength-accept">HTML 5.1<br />
<span class="small">The definition of 'minlength attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `html.elements.attribute.minlength`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`maxlength`](maxlength)
-   [`size`](size)
-   [`pattern`](pattern)
-   [Constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation)
-   [Constraint validation API](https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation)
-   [`<input>`](../element/input)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/minlength" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/minlength</a>
