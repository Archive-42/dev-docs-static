ValidityState
=============

The `ValidityState` interface represents the *validity states* that an element can be in, with respect to constraint validation. Together, they help explain why an element's value fails to validate, if it's not valid.

Properties
----------

For each of these Boolean properties, a value of `true` indicates that the specified reason validation may have failed is true, with the exception of the `valid` property, which is `true` if the element's value obeys all constraints.

 [`badInput`](validitystate/badinput) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the user has provided input that the browser is unable to convert.

 `customError` <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the element's custom validity message has been set to a non-empty string by calling the element's [`setCustomValidity()`](htmlobjectelement/setcustomvalidity) method.

 [`patternMismatch`](validitystate/patternmismatch) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the value does not match the specified [`pattern`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-pattern), and `false` if it does match. If `true`, the element matches the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) CSS pseudo-class.

 [`rangeOverflow`](validitystate/rangeoverflow) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the value is greater than the maximum specified by the [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max) attribute, or `false` if it is less than or equal to the maximum. If `true`, the element matches the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) and [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range) and CSS pseudo-classes.

 [`rangeUnderflow`](validitystate/rangeunderflow) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the value is less than the minimum specified by the [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min) attribute, or `false` if it is greater than or equal to the minimum. If `true`, the element matches the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) and [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range) CSS pseudo-classes.

 [`stepMismatch`](validitystate/stepmismatch) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the value does not fit the rules determined by the [`step`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-step) attribute (that is, it's not evenly divisible by the step value), or `false` if it does fit the step rule. If `true`, the element matches the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) and [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range) CSS pseudo-classes.

 [`tooLong`](validitystate/toolong) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the value exceeds the specified `maxlength` for [`HTMLInputElement`](htmlinputelement) or [`HTMLTextAreaElement`](htmltextareaelement) objects, or `false` if its length is less than or equal to the maximum length. ***Note:** This property is never `true` in Gecko, because elements' values are prevented from being longer than `maxlength`.* If `true`, the element matches the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) and [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range) CSS pseudo-classes.

 [`tooShort`](validitystate/tooshort) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the value fails to meet the specified `minlength` for [`HTMLInputElement`](htmlinputelement) or [`HTMLTextAreaElement`](htmltextareaelement) objects, or `false` if its length is greater than or equal to the minimum length. If `true`, the element matches the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) and [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range) CSS pseudo-classes.

 [`typeMismatch`](validitystate/typemismatch) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the value is not in the required syntax (when [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type) is `email` or `url`), or `false` if the syntax is correct. If `true`, the element matches the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) CSS pseudo-class.

 `valid` <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the element meets all its validation constraints, and is therefore considered to be valid, or `false` if it fails any constraint. If `true`, the element matches the [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) CSS pseudo-class; the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) CSS pseudo-class otherwise.

 <span class="page-not-created">`valueMissing`</span> <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the element has a [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-required) attribute, but no value, or `false` otherwise. If `true`, the element matches the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) CSS pseudo-class.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#validitystate">HTML Living Standard<br />
<span class="small">The definition of 'ValidityState' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living Standard</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#validitystate-validitystate">HTML 5.1<br />
<span class="small">The definition of 'ValidityState' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change from the previous snapshot <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/forms.html#validitystate">HTML5<br />
<span class="small">The definition of 'ValidityState' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>First snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a> containing this interface.</td></tr></tbody></table>

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

`ValidityState`

15

12

4

10

12.1

5

4

Yes

4

12.1

5

Yes

`badInput`

25

14

29

No

15

11

4.4

Yes

64

14

7

Yes

`customError`

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

`rangeOverflow`

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

`rangeUnderflow`

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

`stepMismatch`

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

`tooLong`

15

12

Not supported in the unlikely case of the value being initially set too long, and then changed by the user to a still incorrect state. Per caniuse.com.

4

Not supported in the unlikely case of the value being initially set too long, and then changed by the user to a still incorrect state. Per caniuse.com.

10

15

11

4

Yes

64

14

5

Yes

`tooShort`

40

17

51

No

27

11

67

Yes

64

27

10

Yes

`typeMismatch`

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

`valid`

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

`valueMissing`

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

-   [Guide: Constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation)
-   [Tutorial: Form data validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ValidityState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ValidityState</a>
