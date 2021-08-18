HTMLInputElement.stepDown()
===========================

The `HTMLInputElement.stepDown([n])` method decrements the value of a numeric type of [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element by the value of the `step` attribute or up to `n` multiples of the step attribute if a number is passed as the parameter. The method, when invoked, decrements the [`value`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-value) by ([`step`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-step) \* n), where n defaults to 1 if not specified, and `step` defaults to the default value for `step` if not specified.

Valid on all numeric, date, and time input types that support the step attribute, including[date](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date), [month](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/month), [week](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/week), [time](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/time), [datetime-local](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/datetime-local), [number](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/number), and [range](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/range).

Given `<input id="myTime" type="time" max="17:00" step="900" value="17:00">`, invoking `myTime.step(3)` will change the value to 16:15, decrementing the time by `3 * 900`, or 45 minutes. `myTime.step()`, with no parameter, would have resulted in `16:45`, as `n` defaults to `1`.

    <!--  decrements by intervals of 900 seconds (15 minute) -->
    <input type="time" max="17:00" step="900">

    <!-- decrements by intervals of 7 days (one week) -->
    <input type="date" max="2019-12-25" step="7">

    <!-- decrements by intervals of 12 months (one year) -->
    <input type="month" max="2019-12" step="12">

The method, when invoked, changes the form control's value by the value given in the `step` attribute, multiplied by the parameter, within the constraints set within the form control. The default value for the parameter, if not is passed, is 1. The method will not cause the value to go below the `min` value set or defy the constraints set by the `step` attribute. A negative value for `n` will increment the value, but will not increment beyond the `max` value.

If the value before invoking the `stepDown()` method is invalid, for example, if it doesn't match the constraints set by the `step` attribute, invoking the `stepDown()` method will return a value that does match the form controls constraints.

If the form control is non time, date, or numeric in nature, and therefore does not support the `step` attribute (see the list of supported input types in the table above), or if the `step` value is set to `any`, an `InvalidStateError` exception is thrown.

[`HTMLInputElement.stepDown()`](stepdown)  
Decrements the [`value`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-value) by ([`step`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-step) \* n), where n defaults to 1 if not specified. Throws an INVALID\_STATE\_ERR exception:

-   if the method is not applicable to for the current [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type) value,
-   if the element has no [`step`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-step) value,
-   if the [`value`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-value) cannot be converted to a number,
-   if the resulting value is above the [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max) or below the [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min).

Syntax
------

    element.stepDown( [ stepDecrement ] );

### Parameters

*`stepDecrement`*  
The optional `stepDecrement` parameter is a numeric value. If no parameter is passed, *stepDecrement* defaults to 1.

If the value is a float, the value will increment as if `Math.floor(stepDecrement)` was passed. If the value is negative, the value will be incremented instead of decremented.

Example
-------

Click the button in this example to increment the [number](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/number) input type:

### HTML

    <p>
      <label>Enter a number between 0 and 400 that is divisible by 5:
       <input type="number" step="5" id="theNumber" min="0" max="400">
      </label>
    </p>
    <p>
      <label>Enter how many values of step you would like to increment by or leave it blank:
       <input type="number" step="1" id="decrementer" min="-2" max="15">
      </label>
    </p>
    <input type="button" value="Decrement" id="theButton">

### JavaScript

    /* make the button call the function */
    let button = document.getElementById('theButton');
    button.addEventListener('click', function() {
      stepondown();}
    );

    function stepondown() {
      let input = document.getElementById('theNumber');
      let val = document.getElementById('decrementer').value;

      if (val) {  /* increment with a parameter */
        input.stepDown(val);
      } else {    /* or without a parameter. Try it with 0, 5, -2, etc. */
        input.stepDown();
      }
    }

### CSS

    input:invalid {
      border: red solid 3px;
    }

### Result

Note if you don't pass a parameter to the `stepDown()` method, it defaults to 1. Any other value is a multiplier of the `step` attribute value, which in this case is 5. If we pass 4 as the stepDecrement, the input will stepDown by `4 * 5`, or `20`. If the parameter is 0, the number will not be decremented. The stepDown() method will not allow the input to go out of range, in this case stopping when it reaches 0 and rounding down and floats that are passed as a parameter.

Try setting the step decrementer to `1.2`. What happens when you invoke the method?

Try setting the value to `44`, which is not valid. What happens when you invoke the method?

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/input.html#dom-input-stepdown">HTML Living Standard<br />
<span class="small">The definition of 'stepDown()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#dom-htmlinputelement-stepdown">HTML 5.1<br />
<span class="small">The definition of 'stepDown()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#dom-htmlinputelement-stepdown">HTML5<br />
<span class="small">The definition of 'stepDown()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`stepDown`

5

12

16

Does not have a specific UI. There are still differences with the latest spec; see [bug 835773](https://bugzil.la/835773).

10

≤12.1

5

≤37

18

16

Does not have a specific UI. There are still differences with the latest spec; see [bug 835773](https://bugzil.la/835773).

≤12.1

4

1.0

See also
--------

-   [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
-   [`HTMLInputElement`](../htmlinputelement)
-   [`HTMLInputElement.stepUp()`](stepup)
-   `step`, `min` and `max` attributes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepDown" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepDown</a>
