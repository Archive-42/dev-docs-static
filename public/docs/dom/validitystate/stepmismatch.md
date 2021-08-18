ValidityState.stepMismatch
==========================

The read-only `stepMismatch` property of a `ValidityState` object indicates if the value of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), after having been edited by the user, does not conform to the constraints set by the element's `step` attribute.

If the field is numeric in nature, including the [date](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date), [month](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/month), [week](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/week), [time](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/time), [datetime-local](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/datetime-local), [number](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/number) and [range](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/range) types and the step value is not `any`, if the value don't doesn't conform to the constraints set by the `step` and `min` values, then `stepMismatch` will be true. If the remainder of the form control's value less the `min` value, divided by the `step` value (which defaults to 1 if omitted) is not zero, there is a mismatch.

Given the following:

    <input type="number" min="20" max="40" step="2"/>

if `(value - min) % 2 != 0`, `stepMismatch` will be true.

If true, the element matches the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) and [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range) CSS pseudo-classes.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/constraints.html#dom-validitystate-stepmismatch">HTML Living Standard<br />
<span class="small">The definition of 'ValidityState.stepMismatch' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#dom-validitystate-stepmismatch">HTML 5.1<br />
<span class="small">The definition of 'ValidityState.stepMismatch' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-validitystate-stepmismatch">HTML5<br />
<span class="small">The definition of 'ValidityState.stepMismatch' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [Constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation)
-   [Forms: Data form validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
-   [`step` attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/step)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/stepMismatch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/stepMismatch</a>
