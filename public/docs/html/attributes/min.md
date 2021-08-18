HTML attribute: min
===================

The `min` attribute defines the minimum value that is acceptable and valid for the input containing the attribute. If the `value` of the element is less than this, the element fails [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). This value must be less than or equal to the value of the `max` attribute. If a value is specified for `min` that isn't a valid number, the input has no minimum value.

Valid for the numeric input types, including the [date](../element/input/date), [month](../element/input/month), [week](../element/input/week), [time](../element/input/time), [datetime-local](../element/input/datetime-local), [number](../element/input/number) and [range](../element/input/range) types, and the [`<meter>`](../element/meter) element, the `min` attribute is a number that specifies the most negative value a form control to be considered valid.

### Syntax

<table><caption>Syntax for <code>min</code> values by input <code>type</code> </caption><thead><tr class="header"><th>Input type</th><th>Example</th><th>Example</th></tr></thead><tbody><tr class="odd"><td><a href="../element/input/date">date</a></td><td><code class="sourceCode html">yyyy-mm-dd</code></td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;date&quot;</span><span class="ot"> min=</span><span class="st">&quot;2019-12-25&quot;</span><span class="ot"> step=</span><span class="st">&quot;1&quot;</span><span class="kw">&gt;</span></code></td></tr><tr class="even"><td><a href="../element/input/month">month</a></td><td><code class="sourceCode html">yyyy-mm</code></td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;month&quot;</span><span class="ot"> min=</span><span class="st">&quot;2019-12&quot;</span><span class="ot"> step=</span><span class="st">&quot;12&quot;</span><span class="kw">&gt;</span></code></td></tr><tr class="odd"><td><a href="../element/input/week">week</a></td><td><code class="sourceCode html">yyyy-W##</code></td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;week&quot;</span><span class="ot"> min=</span><span class="st">&quot;2019-W23&quot;</span><span class="ot"> step=</span><span class="st">&quot;&quot;</span><span class="kw">&gt;</span></code></td></tr><tr class="even"><td><a href="../element/input/time">time</a></td><td><code class="sourceCode html">hh:mm</code></td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;time&quot;</span><span class="ot"> min=</span><span class="st">&quot;09:00&quot;</span><span class="ot"> step=</span><span class="st">&quot;900&quot;</span><span class="kw">&gt;</span></code></td></tr><tr class="odd"><td><a href="../element/input/datetime-local">datetime-local</a></td><td><code>yyyy-mm-ddThh:mm</code></td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;datetime-local&quot;</span><span class="ot"> min=</span><span class="st">&quot;2019-12-25T19:30&quot;</span><span class="kw">&gt;</span></code></td></tr><tr class="even"><td><a href="../element/input/number">number</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/number">&lt;number&gt;</a></td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;number&quot;</span><span class="ot"> min=</span><span class="st">&quot;0&quot;</span><span class="ot"> step=</span><span class="st">&quot;5&quot;</span><span class="ot"> max=</span><span class="st">&quot;100&quot;</span><span class="kw">&gt;</span></code></td></tr><tr class="odd"><td><a href="../element/input/range">range</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/number">&lt;number&gt;</a></td><td><code class="sourceCode html"><span class="kw">&lt;input</span><span class="ot"> type=</span><span class="st">&quot;range&quot;</span><span class="ot"> min=</span><span class="st">&quot;60&quot;</span><span class="ot"> step=</span><span class="st">&quot;5&quot;</span><span class="ot"> max=</span><span class="st">&quot;100&quot;</span><span class="kw">&gt;</span></code></td></tr></tbody></table>

**Note:** When the data entered by the user doesn't adhere to the min value set, the value is considered invalid in contraint validation and will match the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) and [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range) pseudo-classes.

See [Client-side validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) and [`rangeUnderflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeUnderflow) for more information.

For the [`<meter>`](../element/meter) element, the `min` attribute defines the lower numeric bound of the measured range. This must be less than the minimum value (`max` attribute), if specified. In both cases, if omitted, the value defaults to 1.

<table><caption>Syntax for <code>min</code> values for other elements</caption><thead><tr class="header"><th>Input type</th><th>Syntax</th><th>Example</th></tr></thead><tbody><tr class="odd"><td><a href="../element/meter"><code>&lt;meter&gt;</code></a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/number">&lt;number&gt;</a></td><td><code>&lt;meter id="fuel" min="0" max="100" low="33" high="66" optimum="80" value="40"&gt; at 40/100&lt;/meter&gt;</code></td></tr></tbody></table>

### Impact on step

The value of `min` and `step` define what are valid values, even if the `step` attribute is not included, as `step` defaults to `0`.

We add a big red border around invalid inputs:

    input:invalid {
      border: solid red 3px;
    }

Then define an input with a minimum value of 7.2, omitting the step attribute, wherein it defaults to 1.

    <input id="myNumber" name="myNumber" type="number" min="7.2" value="8">

Because `step` defaults to 1, valid values include `7.2`, `8.2`, `9.2`, and so on. The value 8 is not valid. As we included an invalid value, supporting browsers will show the value as invalid.

If not explicitly included, `step` defaults to 1 for `number` and `range`, and 1 unit type (second, week, month, day) for the date/time input types.

Accessibility concerns
----------------------

Provide instructions to help users understand how to complete the form and use individual form controls. Indicate any required and optional input, data formats, and other relevant information. When using the `min` attribute, ensure this minimum requirement is understood by the user. Providing instructions within the [`<label>`](../element/label) may be sufficient. If providing instructions outside of labels, which allows more flexible positioning and design, consider using `aria-labelledby` or `aria-describedby`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/input.html#the-min-and-max-attributes">HTML Living Standard<br />
<span class="small">The definition of 'min attribute' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/input.html#the-min-and-max-attributes">HTML5<br />
<span class="small">The definition of 'min attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `html.elements.attributes.min`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`step`](step)
-   [`max`](max)
-   other meter attributes: [`low`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/low), [`high`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/high), [`optimum`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/optimum)
-   [Constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation)
-   [Constraint validation API](https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation)
-   [`validityState.rangeUnderflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeUnderflow)
-   [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)
-   [`<input>`](../element/input)
-   [date](../element/input/date), [month](../element/input/month), [week](../element/input/week), [time](../element/input/time), [datetime-local](../element/input/datetime-local), [number](../element/input/number) and [range](../element/input/range) types, and the [`<meter>`](../element/meter)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/min" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/min</a>
