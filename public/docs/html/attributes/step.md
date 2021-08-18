HTML attribute: step
====================

**Draft**

This page is not complete.

The `step` attribute is a number that specifies the granularity that the value must adhere to or the keyword `any`. It is valid for the numeric input types, including the [date](../element/input/date), [month](../element/input/month), [week](../element/input/week), [time](../element/input/time), [datetime-local](../element/input/datetime-local), [number](../element/input/number) and [range](../element/input/range) types.

The `step` sets the *stepping interval* when clicking up and down spinner buttons, moving a slider left and right on a range, and validating the different date types. If not explicitly included, `step` defaults to 1 for `number` and `range`, and 1 unit type (minute, week, month, day) for the date/time input types. The value can must be a positive number - integer or float -- or the special value `any`, which means no stepping is implied, and any value is allowed (barring other constraints, such as `min` and `max`).

The default stepping value for `number` inputs is 1, allowing only integers to be entered, *unless* the stepping base is not an integer. The default stepping value for `time` is 1 second, with 900 being equal to 15 minutes.

### Syntax

<table><caption>Default values for step</caption><thead><tr class="header"><th>Input type</th><th>Value</th><th>Example</th></tr></thead><tbody><tr class="odd"><td><a href="../element/input/date">date</a></td><td>1 (day)</td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;date&quot;</span><span class="ot"> min=</span><span class="st">&quot;2019-12-25&quot;</span><span class="ot"> step=</span><span class="st">&quot;1&quot;</span><span class="kw">&gt;</span></code></td></tr><tr class="even"><td><a href="../element/input/month">month</a></td><td>1 (month)</td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;month&quot;</span><span class="ot"> min=</span><span class="st">&quot;2019-12&quot;</span><span class="ot"> step=</span><span class="st">&quot;12&quot;</span><span class="kw">&gt;</span></code></td></tr><tr class="odd"><td><a href="../element/input/week">week</a></td><td>1 (week)</td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;week&quot;</span><span class="ot"> min=</span><span class="st">&quot;2019-W23&quot;</span><span class="ot"> step=</span><span class="st">&quot;2&quot;</span><span class="kw">&gt;</span></code></td></tr><tr class="even"><td><a href="../element/input/time">time</a></td><td>60 (seconds)</td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;time&quot;</span><span class="ot"> min=</span><span class="st">&quot;09:00&quot;</span><span class="ot"> step=</span><span class="st">&quot;900&quot;</span><span class="kw">&gt;</span></code></td></tr><tr class="odd"><td><a href="../element/input/datetime-local">datetime-local</a></td><td>1 (day)</td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;datetime-local&quot;</span><span class="ot"> min=</span><span class="st">&quot;019-12-25T19:30&quot;</span><span class="ot"> step=</span><span class="st">&quot;7&quot;</span><span class="kw">&gt;</span></code></td></tr><tr class="even"><td><a href="../element/input/number">number</a></td><td>1</td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;number&quot;</span><span class="ot"> min=</span><span class="st">&quot;0&quot;</span><span class="ot"> step=</span><span class="st">&quot;0.1&quot;</span><span class="ot"> max=</span><span class="st">&quot;10&quot;</span><span class="kw">&gt;</span></code></td></tr><tr class="odd"><td><a href="../element/input/range">range</a></td><td>1</td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;range&quot;</span><span class="ot"> min=</span><span class="st">&quot;0&quot;</span><span class="ot"> step=</span><span class="st">&quot;2&quot;</span><span class="ot"> max=</span><span class="st">&quot;10&quot;</span><span class="kw">&gt;</span></code></td></tr></tbody></table>

If `any` is not explicity set, valid values for the `number`, date/time input types, and `range` input types are equal to the basis for stepping - the `min` value and increments of the step value, up to the `max` value, if specified. For example, if we have `<input type="number" min="10" step="2">` any even integer, 10 or great, is valid. If omitted, `<input type="number">`, any integer is valid, but floats, like 4.2, are not valid, as `step` defaults to 1. For 4.2 to be valid, `step` would have had to be set to `any`, 0.1, 0.2, or any the min value would have had to be a number ending in .2, such as `<input type="number" min="-5.2">`

### min impact on step

The value of `min` and `step` define what are valid values, even if the `step` attribute is not included, as `step` defaults to `0`.

We add a big red border around invalid inputs:

    input:invalid {
      border: solid red 3px;
    }

Then define an input with a minimum value of 7.2, omitting the step attribute, wherein it defaults to 1.

    <input id="myNumber" name="myNumber" type="number" step="2" min="1.2">

Valid values include `1.2`, `3.2`, `5.2`, `7.2`, `9.2`, `11.2`, and so on. Integers and even numbers followed by .2 are not valid. As we included an invalid value, supporting browsers will show the value as invalid. The number spinner, if present, will only show valid float values of `1.2` and greater

**Note:** When the data entered by the user doesn't adhere to the stepping configuration, the value is considered invalid in constraint validation and will match the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) and [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range) pseudoclasses

See [Client-side validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) and [`stepMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/stepMismatch) for more information.

Accessibility concerns
----------------------

Provide instructions to help users understand how to complete the form and use individual form controls. Indicate any required and optional input, data formats, and other relevant information. When using the `min` attribute, ensure this minimum requirement is understood by the user. Providing instructions within the [`<label>`](../element/label) may be sufficient. If providing instructions outside of labels, which allows more flexible positioning and design, consider using `aria-labelledby` or `aria-describedby`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/input.html#the-step-attribute">HTML Living Standard<br />
<span class="small">The definition of 'step attribute' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/input.html#the-step-attribute">HTML5<br />
<span class="small">The definition of 'step attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

See also
--------

-   [`max`](max)
-   [`min`](min)
-   [Constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation)
-   [Constraint validation API](https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation)
-   [`validityState.stepMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/stepMismatch)
-   [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)
-   [`<input>`](../element/input)
-   [date](../element/input/date), [month](../element/input/month), [week](../element/input/week), [time](../element/input/time), [datetime-local](../element/input/datetime-local), [number](../element/input/number) and [range](../element/input/range) types, and the [`<meter>`](../element/meter)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/step" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/step</a>
