ValidityState.patternMismatch
=============================

**Draft**

This page is not complete.

The read-only `patternMismatch` property of a `ValidityState` object indicates if the value of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), after having been edited by the user, does not conform to the constraints set by the element's `pattern` attribute.

If the field supports the `pattern` attribute -- which means the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) is of `type` [text](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/text), [tel](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/tel), [email](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/email), [url](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/url), [password](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/password), or [search](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/search) -- and the pattern value is set to a valid regular expression, if the value don't doesn't conform to the constraints set by the `pattern` value, the `patternMismatch` property will be true.

Examples
--------

Given the following:

    <p>
     <label>Enter your phone number in the format (123)456-7890
      (<input name="tel1" type="tel" pattern="[0-9]{3}" placeholder="###" aria-label="3-digit area code" size="2"/>)-
       <input name="tel2" type="tel" pattern="[0-9]{3}" placeholder="###" aria-label="3-digit prefix" size="2"/> -
       <input name="tel3" type="tel" pattern="[0-9]{4}" placeholder="####" aria-label="4-digit number" size="3"/>
     </label>
    </p>

Here we have 3 sections for a north American phone number with an implicit label encompassing all three components of the phone number, expecting 3-digits, 3-digits and 4-digits respectively, as defined by the `pattern` attribute set on each.

If the values are too long or too short, or contain characters that aren't digits, `patternMismatch` will be true. When `true`, the element matches the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) CSS pseudo-classes.

    input:invalid {
      border: red solid 3px;
    }

Note, in this case, we get a `patternMismatch` not a [`validityState.tooLong`](toolong) or [`validityState.tooShort`](tooshort) if the values are too long or too short because it is the pattern that is dictating the length of the value. Had we used `minlength` and `maxlength` attributes instead, we may have seen [`validityState.tooLong`](toolong) or [`validityState.tooShort`](tooshort) being true.

Note: The `email` input type requires, at minimum, a match of `x@y` and the `url` type requires, at minimum, a match to x:, with no pattern attribute present. When invalid, the [`validityState.typeMismatch`](typemismatch) will be true, if there is no pattern attribute (or if the pattern attribute is not valid for that input type).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/constraints.html#dom-validitystate-patternmismatch">HTML Living Standard<br />
<span class="small">The definition of 'ValidityState.patternMismatch' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#dom-validitystate-patternmismatch">HTML 5.1<br />
<span class="small">The definition of 'ValidityState.patternMismatch' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-validitystate-patternmismatch">HTML5<br />
<span class="small">The definition of 'ValidityState.patternMismatch' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`patternMismatch`

15

12

4

10

12.1

5

≤37

18

4

12.1

5

1.0

See also
--------

-   [Constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation)
-   [Forms: Data form validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
-   [Regular Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/patternMismatch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/patternMismatch</a>
