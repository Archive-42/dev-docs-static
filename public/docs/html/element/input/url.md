&lt;input type="url"&gt;
========================

[`<input>`](../input) elements of type `url` are used to let the user enter and edit a URL.

The input value is automatically validated to ensure that it's either empty or a properly-formatted URL before the form can be submitted. The [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) and [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) CSS pseudo-classes are automatically applied as appropriate to visually denote whether the current value of the field is a valid URL or not.

On browsers that don't support inputs of type `url`, a `url` input falls back to being a standard [text](text) input.

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMString"><code>DOMString</code></a> representing a URL, or empty</td></tr><tr class="even"><td><strong>Events</strong></td><td><code>change</code> and <code>input</code></td></tr><tr class="odd"><td><strong>Supported Common Attributes</strong></td><td><a href="../input#attr-autocomplete"><code>autocomplete</code></a>, <a href="../input#attr-list"><code>list</code></a>, <a href="../input#attr-maxlength"><code>maxlength</code></a>, <a href="../input#attr-minlength"><code>minlength</code></a>, <a href="../input#attr-pattern"><code>pattern</code></a>, <a href="../input#attr-placeholder"><code>placeholder</code></a>, <a href="../input#attr-readonly"><code>readonly</code></a>, <a href="../input#attr-required"><code>required</code></a> and <a href="../input#attr-size"><code>size</code></a></td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td><code>list</code>, <code>value</code>, <code>selectionEnd</code>, <code>selectionDirection</code></td></tr><tr class="odd"><td><strong>Methods</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select"><code>select()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setRangeText"><code>setRangeText()</code></a> and <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setSelectionRange"><code>setSelectionRange()</code></a>.</td></tr></tbody></table>

Value
-----

The [`<input>`](../input) element's [`value`](../input#attr-value) attribute contains a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) which is automatically validated as conforming to URL syntax. More specifically, there are two possible value formats that will pass validation:

1.  An empty string ("") indicating that the user did not enter a value or that the value was removed.
2.  A single properly-formed absolute URL. This doesn't necessarily mean the URL address exists, but it is at least formatted correctly. In simple terms, this means `urlscheme://restofurl`.

See [Validation](#validation) for details on how URLs are validated to ensure that they're formatted properly.

Additional attributes
---------------------

In addition to the attributes that operate on all [`<input>`](../input) elements regardless of their type, `url` inputs support the following attributes:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>list</code></td><td>The id of the &lt;datalist&gt; element that contains the optional pre-defined autocomplete options</td></tr><tr class="even"><td><code>maxlength</code></td><td>The maximum number of characters the input should accept</td></tr><tr class="odd"><td><code>minlength</code></td><td>The minimum number of characters long the input can be and still be considered valid</td></tr><tr class="even"><td><code>pattern</code></td><td>A regular expression the input's contents must match in order to be valid</td></tr><tr class="odd"><td><code>placeholder</code></td><td>An exemplar value to display in the input field whenever it is empty</td></tr><tr class="even"><td><code>readonly</code></td><td>A Boolean attribute indicating whether or not the contents of the input should be read-only</td></tr><tr class="odd"><td><code>size</code></td><td>A number indicating how many characters wide the input field should be</td></tr><tr class="even"><td><code>spellcheck</code></td><td>Controls whether or not to enable spell checking for the input field, or if the default spell checking configuration should be used</td></tr></tbody></table>

### `list`

The values of the list attribute is the [`id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id) of a [`<datalist>`](../datalist) element located in the same document. The [`<datalist>`](../datalist) provides a list of predefined values to suggest to the user for this input. Any values in the list that are not compatible with the [`type`](../input#attr-type) are not included in the suggested options. The values provided are suggestions, not requirements: users can select from this predefined list or provide a different value.

### `maxlength`

The maximum number of characters (as UTF-16 code units) the user can enter into the `url` input. This must be an integer value 0 or higher. If no `maxlength` is specified, or an invalid value is specified, the `url` input has no maximum length. This value must also be greater than or equal to the value of `minlength`.

The input will fail [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) if the length of the text value of the field is greater than `maxlength` UTF-16 code units long. Constraint validation is only applied when the value is changed by the user.

### `minlength`

The minimum number of characters (as UTF-16 code units) the user can enter into the `url` input. This must be an non-negative integer value smaller than or equal to the value specified by `maxlength`. If no `minlength` is specified, or an invalid value is specified, the `url` input has no minimum length.

The input will fail [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) if the length of the text entered into the field is fewer than `minlength` UTF-16 code units long. Constraint validation is only applied when the value is changed by the user.

### `pattern`

The `pattern` attribute, when specified, is a regular expression that the input's [`value`](../../global_attributes#attr-value) must match in order for the value to pass [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). It must be a valid JavaScript regular expression, as used by the [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) type, and as documented in our [guide on regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions); the `'u'` flag is specified when compiling the regular expression, so that the pattern is treated as a sequence of Unicode code points, instead of as ASCII. No forward slashes should be specified around the pattern text.

If the specified pattern is not specified or is invalid, no regular expression is applied and this attribute is ignored completely.

**Tip:** Use the [`title`](../input#attr-title) attribute to specify text that most browsers will display as a tooltip to explain what the requirements are to match the pattern. You should also include other explanatory text nearby.

See the section [Pattern validation](#pattern_validation) for details and an example.

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

{{page("/en-US/docs/Web/HTML/Element/input/text", "autocorrect", 0, 1, 2)}}

{{page("/en-US/docs/Web/HTML/Element/input/text", "mozactionhint", 0, 1, 2)}}

Using URL inputs
----------------

When you create a URL input with the proper `type` value, `url`, you get automatic validation that the entered text is at least in the correct form to potentially be a legitimate URL. This can help avoid cases in which the user mis-types their web site's address, or provides an invalid one.

It's important, however, to note that this is not enough to ensure that the specified text is a URL which actually exists, corresponds to the user of the site, or is acceptable in any other way. It ensures that the value of the field is properly formatted to be a URL.

**Note**: It's also crucial to remember that a user can tinker with your HTML behind the scenes, so your site *must not* use this validation for any security purposes. You *must* verify the URL on the server-side of any transaction in which the provided text may have any security implications of any kind.

### A simple URL input

Currently, all browsers which implement this element implement it as a standard text input field with basic validation features. In its most basic form, a URL input can be implemented like this:

    <input id="myURL" name="myURL" type="url">

Notice that it's considered valid when empty and when a single validly-formatted URL address is entered, but is otherwise not considered valid. By adding the [`required`](../input#attr-required) attribute, only properly-formed URLs are allowed; the input is no longer considered valid when empty.

There is nothing magical going on here. Submitting this form would cause the following data to be sent to the server: `myURL=http%3A%2F%2Fwww.example.com`. Note how characters are escaped as necessary.

### Placeholders

Sometimes it's helpful to offer an in-context hint as to what form the input data should take. This can be especially important if the page design doesn't offer descriptive labels for each [`<input>`](../input). This is where **placeholders** come in. A placeholder is a value that demonstrates the form the `value` should take by presenting an example of a valid value, which is displayed inside the edit box when the element's `value` is "". Once data is entered into the box, the placeholder disappears; if the box is emptied, the placeholder reappears.

Here, we have a `url` input with the placeholder `http://www.example.com`. Note how the placeholder disappears and reappears as you manipulate the contents of the edit field.

    <input id="myURL" name="myURL" type="url"
           placeholder="http://www.example.com">

### Controlling the input size

You can control not only the physical length of the input box, but also the minimum and maximum lengths allowed for the input text itself.

#### Physical input element size

The physical size of the input box can be controlled using the [`size`](../input#attr-size) attribute. With it, you can specify the number of characters the input box can display at a time. In this example, for instance, the `url` edit box is 30 characters wide:

    <input id="myURL" name="myURL" type="url"
           size="30">

#### Element value length

The `size` is separate from the length limitation on the entered URL itself. You can specify a minimum length, in characters, for the entered URL using the [`minlength`](../input#attr-minlength) attribute; similarly, use [`maxlength`](../input#attr-maxlength) to set the maximum length of the entered URL. If `maxLength` exceeds `size`, the input box's contents will scroll as needed to show the current selection or insertion point as the content is manipulated.

The example below creates a 30-character wide URL address entry box, requiring that the contents be no shorter than 10 characters and no longer than 80 characters.

    <input id="myURL" name="myURL" type="url"
           size="30" minlength="10" maxlength="80">

**Note**: These attributes also affect validation; a value shorter or longer than the specified minimum/maximum lengths will be classified as invalid; in addition most browsers will refuse to let the user enter a value longer than the specified maximum length.

### Providing default options

As always, you can provide a default value for a `url` input box by setting its [`value`](../input#attr-value) attribute:

    <input id="myURL" name="myURL" type="url"
           value="http://www.example.com">

#### Offering suggested values

Taking it a step farther, you can provide a list of default options from which the user can select by specifying the [`list`](../input#attr-list) attribute. This doesn't limit the user to those options, but does allow them to select commonly-used URLs more quickly. This also offers hints to [`autocomplete`](../input#attr-autocomplete). The `list` attribute specifies the ID of a [`<datalist>`](../datalist), which in turn contains one [`<option>`](../option) element per suggested value; each `option`'s `value` is the corresponding suggested value for the URL entry box.

    <input id="myURL" name="myURL" type="url"
           list="defaultURLs">

    <datalist id="defaultURLs">
      <option value="https://developer.mozilla.org/">
      <option value="http://www.google.com/">
      <option value="http://www.microsoft.com/">
      <option value="https://www.mozilla.org/">
      <option value="http://w3.org/">
    </datalist>

With the [`<datalist>`](../datalist) element and its [`<option>`](../option)s in place, the browser will offer the specified values as potential values for the URL; this is typically presented as a popup or drop-down menu containing the suggestions. While the specific user experience may vary from one browser to another, typically clicking in the edit box presents a drop-down of the suggested URLs. Then, as the user types, the list is adjusted to show only matching values. Each typed character narrows down the list until the user makes a selection or types a custom value.

#### Using labels for suggested values

You can opt to include the [`label`](../option#attr-label) attribute on one or all of your `<option>` elements to provide textual labels. Some browsers may display only the labels, while others may display both the label and the URL.

    <input id="myURL" name="myURL" type="url"
           list="defaultURLs">

    <datalist id="defaultURLs">
      <option value="https://developer.mozilla.org/" label="MDN Web Docs">
      <option value="http://www.google.com/" label="Google">
      <option value="http://www.microsoft.com/" label="Microsoft">
      <option value="https://www.mozilla.org/" label="Mozilla">
      <option value="http://w3.org/" label="W3C">
    </datalist>

Validation
----------

There are two levels of content validation available for `url` inputs. First, there's the standard level of validation offered to all [`<input>`](../input)s, which automatically ensures that the contents meet the requirements to be a valid URL. But there's also the option to add additional filtering to ensure that your own specialized needs are met, if you have any.

**Important**: HTML form validation is *not* a substitute for scripts that ensure that the entered data is in the proper format. It's far too easy for someone to make adjustments to the HTML that allow them to bypass the validation, or to remove it entirely. It's also possible for someone to bypass your HTML entirely and submit the data directly to your server. If your server-side code fails to validate the data it receives, disaster could strike when improperly-formatted data (or data which is too large, is of the wrong type, and so forth) is entered into your database.

### Basic validation

Browsers that support the `url` input type automatically provide validation to ensure that only text that matches the standard format for URLs is entered into the input box.

The syntax of a URL is fairly intricate. It's defined by WHATWG's [URL Living Standard](https://url.spec.whatwg.org/) and is described for newcomers in our article [What is a URL?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL)

### Making a URL required

As mentioned earlier, to make a URL entry required before the form can be submitted (you can't leave the field blank), you just need to include the [`required`](../input#attr-required) attribute on the input.

    <form>
      <input id="myURL" name="myURL" type="url" required>
      <button>Submit</button>
    </form>

Try submitting the above form with no value entered to see what happens.

### Pattern validation

If you need the entered URL to be restricted further than just "any string that looks like a URL," you can use the [`pattern`](../input#attr-pattern) attribute to specify a [regular expression](https://developer.mozilla.org/en-US/docs/Glossary/Regular_expression) the value must match for the value to be valid.

For example, let's say you're building a support page for employees of Myco, Inc. which will let them contact their IT department for help if one of their pages has a problem. In our simplified form, the user needs to enter the URL of the page that has a problem, and a message describing what is wrong. But we want the URL to only successfully validate if the entered URL is in a Myco domain.

Since inputs of type `url` validate against both the standard URL validation *and* the specified [`pattern`](../input#attr-pattern), you can implement this easily. Let's see how:

    <form>
      <div>
        <label for="myURL">Enter the problem website address:</label>
        <input id="myURL" name="myURL" type="url"
               required pattern=".*\.myco\..*"
               title="The URL must be in a Myco domain">
        <span class="validity"></span>
      </div>
      <div>
        <label for="myComment">What is the problem?</label>
        <input id="myComment" name="myComment" type="text"
               required>
        <span class="validity"></span>
      </div>
      <div>
        <button>Submit</button>
      </div>
    </form>

First of all, the [`required`](../input#attr-required) attribute is specified, making it mandatory that a valid email address be provided.

Second, in the `url` input we set `pattern` to `".*\.myco\..*"`. This simple regular expression requests a string that has any number of characters, followed by a dot, followed by "myco", followed by a dot, followed by any number of characters. And because the browser runs both the standard URL filter *and* our custom pattern against the specified text, we wind up with a validation which says "make sure this is a valid URL, and also in a Myco domain."

This isn't perfect, but it is good enough for this simple demo's requirements.

It's advisable to use the [`title`](../../global_attributes#attr-title) attribute along with `pattern`. If you do, the `title` *must* describe the pattern; it should explain what format the data should take on, rather than any other information. That's because the `title` may be displayed or spoken as part of a validation error message. For example, the browser might present the message "The entered text doesn't match the required pattern." followed by your specified `title`. If your `title` is something like "URL", the result would be the message "The entered text doesn't match the required pattern. URL", which is not a good user experience.

That's why, instead, we specify the string "The URL must be in a myco domain". By doing that, the resulting full error message might be something like "The entered text doesn't match the required pattern. The URL should be in a myco domain."

**Note**: If you run into trouble while writing your validation regular expressions and they're not working properly, check your browser's console; there may be helpful error messages there to aid you in solving the problem.

Examples
--------

There's not much else to say about `url` type inputs; check the [Pattern validation](#pattern_validation) and [Using URL inputs](#using_url_inputs) sections for numerous examples.

You can also find our [pattern validation example on GitHub](https://github.com/mdn/learning-area/blob/master/html/forms/url-example/index.html) (see it [running live also](https://mdn.github.io/learning-area/html/forms/url-example/)).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#url-state-(type=url)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="url"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#url-state-typeurl">HTML 5.1<br />
<span class="small">The definition of '&lt;input type="url"&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr><tr class="odd"><td><a href="https://url.spec.whatwg.org/#urls">URL<br />
<span class="small">The definition of 'URL syntax' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living Standard</td></tr></tbody></table>

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

`url`

1

12

Yes

10

11

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
-   `<input type="email">`
-   [Compatibility of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/url" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/url</a>
