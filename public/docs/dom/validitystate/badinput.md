validityState.badInput
======================

The read-only `badInput` property of a [ValidityState](../validitystate) object indicates if the user has provided input that the browser is unable to convert. For example, if you have a number input element whose content is a string. ***Note:** While this is unsupported in Internet Explorer, any non-numeric value will be dismissed from the field if it is a number input.*

Example
-------

    <input type="number" id="age">

    var input = document.getElementById("age");
    if (input.validity.badInput) {
      console.log("Bad input detected…");
    } else {
      console.log("Content of input ok.");
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/constraints.html#dom-validitystate-badinput">HTML Living Standard<br />
<span class="small">The definition of 'ValidityState.badInput' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Live Standard</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#dom-validitystate-badinput">HTML 5.1<br />
<span class="small">The definition of 'ValidityState.badInput' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change from the previous snapshot <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-validitystate-badinput">HTML5<br />
<span class="small">The definition of 'ValidityState.badInput' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>First snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a> containing this interface.</td></tr></tbody></table>

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

See also
--------

-   [Guide: Constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation)
-   [Tutorial: Form data validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/badInput" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/badInput</a>
