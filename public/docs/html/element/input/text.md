&lt;input type="text"&gt;
=========================

[`<input>`](../input) elements of type `text` create basic single-line text fields.

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMString"><code>DOMString</code></a> representing the text contained in the text field.</td></tr><tr class="even"><td><strong>Events</strong></td><td><code>change</code> and <code>input</code></td></tr><tr class="odd"><td><strong>Supported Common Attributes</strong></td><td><a href="../input#attr-autocomplete"><code>autocomplete</code></a>, <a href="../input#attr-list"><code>list</code></a>, <a href="../input#attr-maxlength"><code>maxlength</code></a>, <a href="../input#attr-minlength"><code>minlength</code></a>, <a href="../input#attr-pattern"><code>pattern</code></a>, <a href="../input#attr-placeholder"><code>placeholder</code></a>, <a href="../input#attr-readonly"><code>readonly</code></a>, <a href="../input#attr-required"><code>required</code></a> and <a href="../input#attr-size"><code>size</code></a></td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td><a href="../input#attr-list"><code>list</code></a>, <code>value</code></td></tr><tr class="odd"><td><strong>Methods</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select"><code>select()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setRangeText"><code>setRangeText()</code></a> and <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setSelectionRange"><code>setSelectionRange()</code></a>.</td></tr></tbody></table>

Value
-----

The [`value`](../input#attr-value) attribute is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) that contains the current value of the text entered into the text field. You can retrieve this using the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) `value` property in JavaScript.

    let theText = myTextInput.value;

If no validation constraints are in place for the input (see [Validation](#validation) for more details), the value may be an empty string ("").

Additional attributes
---------------------

In addition to the attributes that operate on all [`<input>`](../input) elements regardless of their type, text inputs support the following attributes:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>list</code></td><td>The id of the &lt;datalist&gt; element that contains the optional pre-defined autocomplete options</td></tr><tr class="even"><td><code>maxlength</code></td><td>The maximum number of characters the input should accept</td></tr><tr class="odd"><td><code>minlength</code></td><td>The minimum number of characters long the input can be and still be considered valid</td></tr><tr class="even"><td><code>pattern</code></td><td>A regular expression the input's contents must match in order to be valid</td></tr><tr class="odd"><td><code>placeholder</code></td><td>An exemplar value to display in the input field whenever it is empty</td></tr><tr class="even"><td><code>readonly</code></td><td>A Boolean attribute indicating whether or not the contents of the input should be read-only</td></tr><tr class="odd"><td><code>size</code></td><td>A number indicating how many characters wide the input field should be</td></tr><tr class="even"><td><code>spellcheck</code></td><td>Controls whether or not to enable spell checking for the input field, or if the default spell checking configuration should be used</td></tr></tbody></table>

### `list`

The values of the list attribute is the [`id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id) of a [`<datalist>`](../datalist) element located in the same document. The [`<datalist>`](../datalist) provides a list of predefined values to suggest to the user for this input. Any values in the list that are not compatible with the [`type`](../input#attr-type) are not included in the suggested options. The values provided are suggestions, not requirements: users can select from this predefined list or provide a different value.

### `maxlength`

The maximum number of characters (as UTF-16 code units) the user can enter into the `text` input. This must be an integer value 0 or higher. If no `maxlength` is specified, or an invalid value is specified, the `text` input has no maximum length. This value must also be greater than or equal to the value of `minlength`.

The input will fail [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) if the length of the text value of the field is greater than `maxlength` UTF-16 code units long. Constraint validation is only applied when the value is changed by the user.

### `minlength`

The minimum number of characters (as UTF-16 code units) the user can enter into the `text` input. This must be an non-negative integer value smaller than or equal to the value specified by `maxlength`. If no `minlength` is specified, or an invalid value is specified, the `text` input has no minimum length.

The input will fail [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) if the length of the text entered into the field is fewer than `minlength` UTF-16 code units long. Constraint validation is only applied when the value is changed by the user.

### `pattern`

The `pattern` attribute, when specified, is a regular expression that the input's [`value`](../../global_attributes#attr-value) must match in order for the value to pass [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). It must be a valid JavaScript regular expression, as used by the [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) type, and as documented in our [guide on regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions); the `'u'` flag is specified when compiling the regular expression, so that the pattern is treated as a sequence of Unicode code points, instead of as ASCII. No forward slashes should be specified around the pattern text.

If the specified pattern is not specified or is invalid, no regular expression is applied and this attribute is ignored completely.

**Tip:** Use the [`title`](../input#attr-title) attribute to specify text that most browsers will display as a tooltip to explain what the requirements are to match the pattern. You should also include other explanatory text nearby.

See [Specifying a pattern](#specifying_a_pattern) for further details and an example.

### `placeholder`

The `placeholder` attribute is a string that provides a brief hint to the user as to what kind of information is expected in the field. It should be a word or short phrase that demonstrates the expected type of data, rather than an explanatory message. The text *must not* include carriage returns or line feeds.

If the control's content has one directionality ([LTR](https://developer.mozilla.org/en-US/docs/Glossary/ltr) or [RTL](https://developer.mozilla.org/en-US/docs/Glossary/rtl)) but needs to present the placeholder in the opposite directionality, you can use Unicode bidirectional algorithm formatting characters to override directionality within the placeholder; see [Overriding BiDi using Unicode control characters](https://developer.mozilla.org/en-US/docs/Web/Guide/Unicode_Bidrectional_Text_Algorithm#overriding_bidi_using_unicode_control_characters) in [The Unicode Bidirectional Text Algorithm](https://developer.mozilla.org/en-US/docs/Web/Guide/Unicode_Bidrectional_Text_Algorithm) for those characters.

**Note:** Avoid using the `placeholder` attribute if you can. It is not as semantically useful as other ways to explain your form, and can cause unexpected technical issues with your content. See [Labels and placeholders](../input#labels_and_placeholders) in [&lt;input&gt;: The Input (Form Input) element](../input) for more information.

### `readonly`

A Boolean attribute which, if present, means this field cannot be edited by the user. Its `value` can, however, still be changed by JavaScript code directly setting the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) `value` property.

**Note:** Because a read-only field cannot have a value, `required` does not have any effect on inputs with the `readonly` attribute also specified.

### `size`

The `size` attribute is a numeric value indicating how many characters wide the input field should be. The value must be a number greater than zero, and the default value is 20. Since character widths vary, this may or may not be exact and should not be relied upon to be so; the resulting input may be narrower or wider than the specified number of characters, depending on the characters and the font ([`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) settings in use).

This does *not* set a limit on how many characters the user can enter into the field. It only specifies approximately how many can be seen at a time. To set an upper limit on the length of the input data, use the `maxlength` attribute.

### `spellcheck`

`spellcheck` is a global attribute which is used to indicate whether or not to enable spell checking for an element. It can be used on any editable content, but here we consider specifics related to the use of `spellcheck` on [`<input>`](../input) elements. The permitted values for `spellcheck` are:

`false`  
Disable spell checking for this element.

`true`  
Enable spell checking for this element.

"" (empty string) or no value  
Follow the element's default behavior for spell checking. This may be based upon a parent's `spellcheck` setting or other factors.

An input field can have spell checking enabled if it doesn't have the [readonly](#readonly) attribute set and is not disabled.

The value returned by reading `spellcheck` may not reflect the actual state of spell checking within a control, if the [user agent's](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) preferences override the setting.

Non-standard attributes
-----------------------

The following non-standard attributes are also available on some browsers. As a general rule, you should avoid using them unless it can't be helped.

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>autocorrect</code></td><td>A string indicating whether or not autocorrect is <code>on</code> or <code>off</code>. <strong>Safari only.</strong></td></tr><tr class="even"><td><code>mozactionhint</code></td><td>A string indicating the type of action that will be taken when the user presses the Enter or Return key while editing the field; this is used to determine an appropriate label for that key on a virtual keyboard. <strong>Firefox for Android only.</strong></td></tr></tbody></table>

### `autocorrect` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>

A Safari extension, the `autocorrect` attribute is a string which indicates whether or not to activate automatic correction while the user is editing this field. Permitted values are:

`on`  
Enable automatic correction of typos, as well as processing of text substitutions if any are configured.

`off`  
Disable automatic correction and text substitutions.

### `mozactionhint` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>

A Mozilla extension, supported by Firefox for Android, which provides a hint as to what sort of action will be taken if the user presses the Enter or Return key while editing the field. This information is used to decide what kind of label to use on the Enter key on the virtual keyboard.

**Note:** This [has been standardized](https://html.spec.whatwg.org/#input-modalities:-the-enterkeyhint-attribute) as the global attribute [`enterkeyhint`](../../global_attributes#attr-enterkeyhint), but is not yet widely implemented. To see the status of the change being implemented in Firefox, see [bug 1490661](https://bugzilla.mozilla.org/show_bug.cgi?id=1490661).

Permitted values are: `go`, `done`, `next`, `search`, and `send`. The browser decides, using this hint, what label to put on the enter key.

Using text inputs
-----------------

`<input>` elements of type `text` create basic, single-line inputs. You should use them anywhere you want the user to enter a single-line value and there isn't a more specific input type available for collecting that value (for example, if it's a [date](datetime-local), [URL](url), [email](email), or [search term](search), you've got better options available).

### Basic example

    <form>
      <div>
        <label for="uname">Choose a username: </label>
        <input type="text" id="uname" name="name">
      </div>
      <div>
        <button>Submit</button>
      </div>
    </form>

This renders like so:

When submitted, the data name/value pair sent to the server will be `name=Chris` (if "Chris" was entered as the input value before submission). You must remember to include [`name`](../input#attr-name) attribute on the [`<input>`](../input) element, otherwise the text field's value won't be included with the submitted data.

### Setting placeholders

You can provide a useful placeholder inside your text input that can provide a hint as to what to enter by including using the [`placeholder`](../input#attr-placeholder) attribute. Look at the following example:

    <form>
      <div>
        <label for="uname">Choose a username: </label>
        <input type="text" id="uname" name="name"
               placeholder="Lower case, all one word">
      </div>
      <div>
        <button>Submit</button>
      </div>
    </form>

You can see how the placeholder is rendered below:

The placeholder is typically rendered in a lighter color than the element's foreground color, and automatically vanishes when the user begins to enter text into the field (or whenever the field has a value set programmatically by setting its `value` attribute.

### Physical input element size

The physical size of the input box can be controlled using the [`size`](../input#attr-size) attribute. With it, you can specify the number of characters the text input can display at a time. This affects the width of the element, letting you specify the width in terms of characters rather than pixels. In this example, for instance, the input is 30 characters wide:

    <form>
      <div>
        <label for="uname">Choose a username: </label>
        <input type="text" id="uname" name="name"
               placeholder="Lower case, all one word"
               size="30">
      </div>
      <div>
        <button>Submit</button>
      </div>
    </form>

Validation
----------

`<input>` elements of type `text` have no automatic validation applied to them (since a basic text input needs to be capable of accepting any arbitrary string), but there are some client-side validation options available, which we'll discuss below.

**Note**: HTML form validation is *not* a substitute for server-scripts that ensure the entered data is in the proper format. It's far too easy for someone to make adjustments to the HTML that allow them to bypass the validation, or to remove it entirely. It's also possible for someone to bypass your HTML entirely and submit the data directly to your server. If your server-side code fails to validate the data it receives, disaster could strike when improperly-formatted data (or data which is too large, is of the wrong type, and so forth) is entered into your database.

### A note on styling

There are useful pseudo-classes available for styling form elements to help the user see when their values are valid or invalid. These are [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) and [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid). In this section, we'll use the following CSS, which will place a check (tick) mark next to inputs containing valid values, and a cross (X) next to inputs containing invalid values.

    div {
      margin-bottom: 10px;
      position: relative;
    }

    input + span {
      padding-right: 30px;
    }

    input:invalid+span:after {
      position: absolute; content: '✖';
      padding-left: 5px;
    }

    input:valid+span:after {
      position: absolute;
      content: '✓';
      padding-left: 5px;
    }

The technique also requires a [`<span>`](../span) element to be placed after the form element, which acts as a holder for the icons. This was necessary because some input types on some browsers don't display icons placed directly after them very well.

### Making input required

You can use the [`required`](../input#attr-required) attribute as an easy way of making entering a value required before form submission is allowed:

    <form>
      <div>
        <label for="uname">Choose a username: </label>
        <input type="text" id="uname" name="name" required>
        <span class="validity"></span>
      </div>
      <div>
        <button>Submit</button>
      </div>
    </form>

This renders like so:

If you try to submit the form with no search term entered into it, the browser will show an error message.

### Input value length

You can specify a minimum length (in characters) for the entered value using the [`minlength`](../input#attr-minlength) attribute; similarly, use [`maxlength`](../input#attr-maxlength) to set the maximum length of the entered value, in characters.

The example below requires that the entered value be 4–8 characters in length.

    <form>
      <div>
        <label for="uname">Choose a username: </label>
        <input type="text" id="uname" name="name" required size="10"
               placeholder="Username"
               minlength="4" maxlength="8">
        <span class="validity"></span>
      </div>
      <div>
        <button>Submit</button>
      </div>
    </form>

This renders like so:

If you try to submit the form with less than 4 characters, you'll be given an appropriate error message (which differs between browsers). If you try to enter more than 8 characters, the browser won't let you.

**Note:** If you specify a `minlength` but do not specify `required`, the input is considered valid, since the user is not required to specify a value.

### Specifying a pattern

You can use the [`pattern`](../input#attr-pattern) attribute to specify a regular expression that the inputted value must match in order to be considered valid (see [Validating against a regular expression](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#validating_against_a_regular_expression) for a simple crash course on using regular expressions to validate inputs).

The example below restricts the value to 4-8 characters and requires that it contain only lower-case letters.

    <form>
      <div>
        <label for="uname">Choose a username: </label>
        <input type="text" id="uname" name="name" required size="45"
               pattern="[a-z]{4,8}">
        <span class="validity"></span>
        <p>Usernames must be lowercase and 4-8 characters in length.</p>
      </div>
      <div>
        <button>Submit</button>
      </div>
    </form>

This renders like so:

Examples
--------

You can see good examples of text inputs used in context in our [Your first HTML form](https://developer.mozilla.org/en-US/docs/Learn/Forms/Your_first_form) and [How to structure an HTML form](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_structure_a_web_form) articles.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/input.html#text-(type=text)-state-and-search-state-(type=search)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="text"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#text-typetext-state-and-search-state-typesearch">HTML 5.1<br />
<span class="small">The definition of '&lt;input type="text"&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`text`

1

12

1

Yes

Yes

1

Yes

Yes

4

Yes

Yes

Yes

See also
--------

-   [HTML Forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)
-   [`<input>`](../input) and the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) interface it's based upon.
-   `<input type="search">`
-   [`<textarea>`](../textarea): Multi-line text input
-   [Compatibility of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/text" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/text</a>
