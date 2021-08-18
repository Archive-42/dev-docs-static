&lt;input type="number"&gt;
===========================

[`<input>`](../input) elements of type `number` are used to let the user enter a number. They include built-in validation to reject non-numerical entries. The browser may opt to provide stepper arrows to let the user increase and decrease the value using their mouse or by tapping with a fingertip.

On browsers that don't support inputs of type `number`, a `number` input falls back to type `text`.

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number"><code>Number</code></a> representing a number, or empty</td></tr><tr class="even"><td><strong>Events</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event"><code>change</code></a> and <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event"><code>input</code></a></td></tr><tr class="odd"><td><strong>Supported common attributes</strong></td><td><a href="../input#attr-autocomplete"><code>autocomplete</code></a>, <a href="../input#attr-list"><code>list</code></a>, <a href="../input#attr-placeholder"><code>placeholder</code></a>, <a href="../input#attr-readonly"><code>readonly</code></a></td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td><code>list</code>, <code>value</code>, <code>valueAsNumber</code></td></tr><tr class="odd"><td><strong>Methods</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select"><code>select()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepUp"><code>stepUp()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepDown"><code>stepDown()</code></a></td></tr></tbody></table>

Value
-----

A [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the value of the number entered into the input. You can set a default value for the input by including a number inside the [`value`](../input#attr-value) attribute, like so:

    <input id="number" type="number" value="42">

Additional attributes
---------------------

In addition to the attributes commonly supported by all [`<input>`](../input) types, inputs of type `number` support these attributes:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>list</code></td><td>The <code>id</code> of the <a href="../datalist"><code>&lt;datalist&gt;</code></a> element that contains the optional pre-defined autocomplete options</td></tr><tr class="even"><td><code>max</code></td><td>The maximum value to accept for this input</td></tr><tr class="odd"><td><code>min</code></td><td>The minimum value to accept for this input</td></tr><tr class="even"><td><code>placeholder</code></td><td>An example value to display inside the field when it's empty</td></tr><tr class="odd"><td><code>readonly</code></td><td>A Boolean attribute indicating whether the value is read-only</td></tr><tr class="even"><td><code>step</code></td><td>A stepping interval to use when using up and down arrows to adjust the value, as well as for validation</td></tr></tbody></table>

### `list`

The values of the list attribute is the [`id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id) of a [`<datalist>`](../datalist) element located in the same document. The [`<datalist>`](../datalist) provides a list of predefined values to suggest to the user for this input. Any values in the list that are not compatible with the [`type`](../input#attr-type) are not included in the suggested options. The values provided are suggestions, not requirements: users can select from this predefined list or provide a different value.

### `max`

The maximum value to accept for this input. If the [`value`](../input#attr-value) entered into the element exceeds this, the element fails [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). If the value of the `max` attribute isn't a number, then the element has no maximum value.

This value must be greater than or equal to the value of the `min` attribute.

### `min`

The minimum value to accept for this input. If the [`value`](../input#attr-value) of the element is less than this, the element fails [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). If a value is specified for `min` that isn't a valid number, the input has no minimum value.

This value must be less than or equal to the value of the `max` attribute.

### `placeholder`

The `placeholder` attribute is a string that provides a brief hint to the user as to what kind of information is expected in the field. It should be a word or short phrase that demonstrates the expected type of data, rather than an explanatory message. The text *must not* include carriage returns or line feeds.

If the control's content has one directionality ([LTR](https://developer.mozilla.org/en-US/docs/Glossary/ltr) or [RTL](https://developer.mozilla.org/en-US/docs/Glossary/rtl)) but needs to present the placeholder in the opposite directionality, you can use Unicode bidirectional algorithm formatting characters to override directionality within the placeholder; see [Overriding BiDi using Unicode control characters](https://developer.mozilla.org/en-US/docs/Web/Guide/Unicode_Bidrectional_Text_Algorithm#overriding_bidi_using_unicode_control_characters) in [The Unicode Bidirectional Text Algorithm](https://developer.mozilla.org/en-US/docs/Web/Guide/Unicode_Bidrectional_Text_Algorithm) for those characters.

**Note:** Avoid using the `placeholder` attribute if you can. It is not as semantically useful as other ways to explain your form, and can cause unexpected technical issues with your content. See [Labels and placeholders](../input#labels_and_placeholders) in [&lt;input&gt;: The Input (Form Input) element](../input) for more information.

### `readonly`

A Boolean attribute which, if present, means this field cannot be edited by the user. Its `value` can, however, still be changed by JavaScript code directly setting the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) `value` property.

**Note:** Because a read-only field cannot have a value, `required` does not have any effect on inputs with the `readonly` attribute also specified.

### `step`

The `step` attribute is a number that specifies the granularity that the value must adhere to, or the special value `any`, which is described below. Only values which are equal to the basis for stepping (`min` if specified, [`value`](../input#attr-value) otherwise, and an appropriate default value if neither of those is provided) are valid.

A string value of `any` means that no stepping is implied, and any value is allowed (barring other constraints, such as `min` and `max`).

**Note:** When the data entered by the user doesn't adhere to the stepping configuration, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) may round to the nearest valid value, preferring numbers in the positive direction when there are two equally close options.

The default stepping value for `number` inputs is `1`, allowing only integers to be entered—*unless* the stepping base is not an integer.

Using number inputs
-------------------

`<input type="number">` elements can help simplify your work when building the user interface and logic for entering numbers into a form. When you create a number input with the proper `type` value, `number`, you get automatic validation that the entered text is a number, and usually a set of up and down buttons to step the value up and down.

**Important**: Bear in mind that, logically, you should not be able to enter characters inside a number input other than numbers. There seems to be some disagreement about this among browsers; see [bug 1398528](https://bugzilla.mozilla.org/show_bug.cgi?id=1398528).

**Note**: It's crucial to remember that a user can tinker with your HTML behind the scenes, so your site *must not* use simple client-side validation for any security purposes. You *must* verify on the server side any transaction in which the provided value may have security implications of any kind.

Mobile browsers further help with the user experience by showing a special keyboard more suited for entering numbers when the user tries to enter a value. The following screenshot is taken from Firefox for Android:

<img src="data:image/png;base64,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" width="360" height="640" />

### A simple number input

In its most basic form, a number input can be implemented like this:

    <label for="ticketNum">Number of tickets you would like to buy:</label>
    <input id="ticketNum" type="number" name="ticketNum" value="0">

A number input is considered valid when empty and when a single number is entered, but is otherwise invalid. If the [`required`](../input#attr-required) attribute is used, the input is no longer considered valid when empty.

**Note**: Any number is an acceptable value, as long as it is a [valid floating point number](https://html.spec.whatwg.org/multipage/infrastructure.html#valid-floating-point-number) (that is, not [NaN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) or [Infinity](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity)).

### Placeholders

Sometimes it's helpful to offer an in-context hint as to what form the input data should take. This can be especially important if the page design doesn't offer descriptive labels for each [`<input>`](../input). This is where **placeholders** come in. A placeholder is a value most commonly used to provide a hint as to the format the input should take `value`. It is displayed inside the edit box when the element's `value` is `""`. Once data is entered into the box, the placeholder disappears; if the box is emptied, the placeholder reappears.

Here, we have an `number` input with the placeholder "`Multiple of 10`". Note how the placeholder disappears and reappears as you manipulate the contents of the edit field.

    <input type="number" placeholder="Multiple of 10">

### Controlling step size

By default, the up and down buttons provided for you to step the number up and down will step the value up and down by 1. You can change this by providing a [`step`](../input#attr-step) attribute, which takes as its value a number specifying the step amount. Our above example contains a placeholder saying that the value should be a multiple of 10, so it makes sense to add a `step` value of `10`:

    <input type="number" placeholder="multiple of 10" step="10">

In this example, you should find that the up and down step arrows will increase and decrease the value by 10 each time, not 1. You can still manually enter a number that's not a multiple of 10, but it will be considered invalid.

### Specifying minimum and maximum values

You can use the [`min`](../input#attr-min) and [`max`](../input#attr-max) attributes to specify a minimum and maximum value that the field can have. For example, let's give our example a minimum of `0`, and a maximum of `100`:

    <input type="number" placeholder="multiple of 10" step="10" min="0" max="100">

In this updated version, you should find that the up and down step buttons will not allow you to go below 0 or above 100. You can still manually enter a number outside these bounds, but it will be considered invalid.

### Allowing decimal values

One issue with number inputs is that their step size is 1 by default. If you try to enter a number with a decimal (such as "1.0"), it will be considered invalid. If you want to enter a value that requires decimals, you'll need to reflect this in the `step` value (e.g. `step="0.01"` to allow decimals to two decimal places). Here's a simple example:

    <input type="number" placeholder="1.0" step="0.01" min="0" max="10">

See that this example allows any value between `0.0` and `10.0`, with decimals to two places. For example, "9.52" is valid, but "9.521" is not.

### Controlling input size

[`<input>`](../input) elements of type `number` don't support form sizing attributes such as [`size`](../input#attr-size). You'll have to resort to [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) to change the size of these controls.

For example, to adjust the width of the input to be only as wide as is needed to enter a three-digit number, we can change our HTML to include an [`id`](../../global_attributes#attr-id) and to shorten our placeholder since the field will be too narrow for the text we have been using so far:

    <input type="number" placeholder="x10" step="10" min="0" max="100" id="number">

Then we add some CSS to narrow the width of the element with the `id` selector `#number`:

    #number {
      width: 3em;
    }

The result looks like this:

### Offering suggested values

You can provide a list of default options from which the user can select by specifying the [`list`](../input#attr-list) attribute, which contains as its value the [`id`](../../global_attributes#attr-id) of a [`<datalist>`](../datalist), which in turn contains one [`<option>`](../option) element per suggested value. Each `option`'s `value` is the corresponding suggested value for the number entry box.

    <input id="ticketNum" type="number" name="ticketNum" list="defaultNumbers">
    <span class="validity"></span>

    <datalist id="defaultNumbers">
      <option value="10045678">
      <option value="103421">
      <option value="11111111">
      <option value="12345678">
      <option value="12999922">
    </datalist>

Validation
----------

We have already mentioned a number of validation features of `number` inputs, but let's review them now:

-   `<input type="number">` elements automatically invalidate any entry that isn't a number (or empty, unless `required` is specified).
-   You can use the [`required`](../input#attr-required) attribute to make an empty entry invalid. (In other words, the input *must* be filled in.)
-   You can use the [`step`](../input#attr-step) attribute to constrain valid values to a certain set of steps (e.g., multiples of 10).
-   You can use the [`min`](../input#attr-min) and [`max`](../input#attr-max) attributes to constrain valid values to lower and upper bounds.

The following example exhibits all of the above features, as well as using some CSS to display valid and invalid icons, depending on the `input`'s value:

    <form>
      <div>
        <label for="balloons">Number of balloons to order (multiples of 10):</label>
        <input id="balloons" type="number" name="balloons" step="10" min="0" max="100" required>
        <span class="validity"></span>
      </div>
      <div>
        <input type="submit">
      </div>
    </form>

Try submitting the form with different invalid values entered — e.g., no value; a value below 0 or above 100; a value that is not a multiple of 10; or a non-numerical value — and see how the error messages the browser gives you differ with different ones.

The CSS applied to this example is as follows:

    div {
      margin-bottom: 10px;
    }

    input:invalid+span:after {
      content: '✖';
      padding-left: 5px;
    }

    input:valid+span:after {
      content: '✓';
      padding-left: 5px;
    }

Here we use the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) and [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) pseudo classes to display an appropriate invalid or valid icon as generated content on the adjacent [`<span>`](../span) element, as a visual indicator of validity.

We put it on a separate `<span>` element for added flexibility. Some browsers don't display generated content very effectively on some types of form inputs. (Read, for example, the section on [`<input type="date">` validation](date#validation).)

**Important**: HTML form validation is *not* a substitute for server-side scripts that ensure that the entered data is in the proper format!

It's far too easy for someone to make adjustments to the HTML that allow them to bypass the validation, or to remove it entirely. It's also possible for someone to bypass your HTML and submit the data directly to your server.

If your server-side code fails to validate the data it receives, disaster could strike when improperly-formatted data is submitted (or data which is too large, is of the wrong type, and so forth).

### Pattern validation

`<input type="number">` elements do not support use of the [`pattern`](../input#attr-pattern) attribute for making entered values conform to a specific regex pattern.

The rationale for this is that number inputs won't be valid if they contain anything except numbers, and you can constrain the minimum and maximum number of valid digits using the [`min`](../input#attr-min) and [`max`](../input#attr-max) attributes (as explained above).

Examples
--------

We've already covered the fact that by default, the increment is `1`, and you can use the [`step`](../input#attr-step) attribute to allow decimal inputs. Let's take a closer look.

In the following example is a form for entering the user's height. It defaults to accepting a height in meters, but you can click the relevant button to change the form to accept feet and inches instead. The input for the height in meters accepts decimals to two places.

The HTML looks like this:

    <form>
        <div class="metersInputGroup">
            <label for="meters">Enter your height — meters:</label>
            <input id="meters" type="number" name="meters" step="0.01" min="0" placeholder="e.g. 1.78" required>
            <span class="validity"></span>
        </div>
        <div class="feetInputGroup" style="display: none;">
            <span>Enter your height — </span>
            <label for="feet">feet:</label>
            <input id="feet" type="number" name="feet" min="0" step="1">
            <span class="validity"></span>
            <label for="inches">inches:</label>
            <input id="inches" type="number" name="inches" min="0" max="11" step="1">
            <span class="validity"></span>
        </div>
        <div>
          <input type="button" class="meters" value="Enter height in feet and inches">
        </div>
        <div>
            <input type="submit" value="Submit form">
        </div>
    </form>

You'll see that we are using many of the attributes we've already looked at in the article earlier on. Since we want to accept a meter value in centimeters, we've set the `step` value to `0.01`, so that values like *1.78* are not seen as invalid. We've also provided a placeholder for that input.

We've hidden the feet and inches inputs initially using `style="display: none;"`, so that meters is the default entry type.

Now, onto the CSS. This looks very similar to the validation styling we saw before; nothing remarkable here.

    div {
      margin-bottom: 10px;
      position: relative;
    }

    input[type="number"] {
      width: 100px;
    }

    input + span {
      padding-right: 30px;
    }

    input:invalid+span:after {
      position: absolute;
      content: '✖';
      padding-left: 5px;
    }

    input:valid+span:after {
      position: absolute;
      content: '✓';
      padding-left: 5px;
    }

And finally, the JavaScript:

    let metersInputGroup = document.querySelector('.metersInputGroup');
    let feetInputGroup = document.querySelector('.feetInputGroup');
    let metersInput = document.querySelector('#meters');
    let feetInput = document.querySelector('#feet');
    let inchesInput = document.querySelector('#inches');
    let switchBtn = document.querySelector('input[type="button"]');

    switchBtn.addEventListener('click', function() {
      if(switchBtn.getAttribute('class') === 'meters') {
        switchBtn.setAttribute('class', 'feet');
        switchBtn.value = 'Enter height in meters';

        metersInputGroup.style.display = 'none';
        feetInputGroup.style.display = 'block';

        feetInput.setAttribute('required', '');
        inchesInput.setAttribute('required', '');
        metersInput.removeAttribute('required');

        metersInput.value = '';
      } else {
        switchBtn.setAttribute('class', 'meters');
        switchBtn.value = 'Enter height in feet and inches';

        metersInputGroup.style.display = 'block';
        feetInputGroup.style.display = 'none';

        feetInput.removeAttribute('required');
        inchesInput.removeAttribute('required');
        metersInput.setAttribute('required', '');

        feetInput.value = '';
        inchesInput.value = '';
      }
    });

After declaring a few variables, an event listener is added to the `button` to control the switching mechanism. This is pretty simple, mostly involving changing over the button's `class` and [`<label>`](../label), and updating the display values of the two sets of inputs when the button is pressed.

(Note that we're not converting back and forth between meters and feet/inches here, which a real-life web application would probably do.)

**Note:** When the user clicks the button, the `required` attribute(s) are removed from the input(s) we are hiding, and empty the `value` attribute(s). This is so the form can be submitted if both input sets aren't filled in. It also ensures that the form won't submit data that the user didn't mean to.

If you didn't do this, you'd have to fill in both feet/inches **and** meters to submit the form!

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#number-state-(type=number)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="number"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#number-state-typenumber">HTML 5.1<br />
<span class="small">The definition of '&lt;input type="number"&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`number`

Yes

12

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [HTML forms guide](https://developer.mozilla.org/en-US/docs/Learn/Forms)
-   [`<input>`](../input)
-   `<input type="tel">`
-   [Compatibility of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/number" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/number</a>
