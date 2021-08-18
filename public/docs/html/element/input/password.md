&lt;input type="password"&gt;
=============================

`<input>` elements of type `password` provide a way for the user to securely enter a password. The element is presented as a one-line plain text editor control in which the text is obscured so that it cannot be read, usually by replacing each character with a symbol such as the asterisk ("\*") or a dot ("•"). This character will vary depending on the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) and <span class="page-not-created">OS</span>.

Specifics of how the entry process works may vary from browser to browser; mobile devices, for example, often display the typed character for a moment before obscuring it, to allow the user to be sure they pressed the key they meant to press; this is helpful given the small size of keys and the ease with which the wrong one can be pressed, especially on virtual keyboards.

**Note:** Any forms involving sensitive information like passwords (e.g. login forms) should be served over HTTPS; Many browsers now implement mechanisms to warn against insecure login forms; see [Insecure passwords](https://developer.mozilla.org/en-US/docs/Web/Security/Insecure_passwords).

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMString"><code>DOMString</code></a> representing a password, or empty</td></tr><tr class="even"><td><strong>Events</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event"><code>change</code></a> and <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event"><code>input</code></a></td></tr><tr class="odd"><td><strong>Supported Common Attributes</strong></td><td><a href="../input#attr-autocomplete"><code>autocomplete</code></a>, <a href="../input#attr-inputmode"><code>inputmode</code></a>, <a href="../input#attr-maxlength"><code>maxlength</code></a>, <a href="../input#attr-minlength"><code>minlength</code></a>, <a href="../input#attr-pattern"><code>pattern</code></a>, <a href="../input#attr-placeholder"><code>placeholder</code></a>, <a href="../input#attr-readonly"><code>readonly</code></a>, <a href="../input#attr-required"><code>required</code></a>, and <a href="../input#attr-size"><code>size</code></a></td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td><code>selectionStart</code>, <code>selectionEnd</code>, <code>selectionDirection</code>, and <code>value</code></td></tr><tr class="odd"><td><strong>Methods</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select"><code>select()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setRangeText"><code>setRangeText()</code></a>, and <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setSelectionRange"><code>setSelectionRange()</code></a></td></tr></tbody></table>

Value
-----

The [`value`](../input#attr-value) attribute contains a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) whose value is the current contents of the text editing control being used to enter the password. If the user hasn't entered anything yet, this value is an empty string (`""`). If the [`required`](../../global_attributes#attr-required) property is specified, then the password edit box must contain a value other than an empty string to be valid.

If the [`pattern`](../input#attr-pattern) attribute is specified, the content of a `password` control is only considered valid if the value passes validation; see [Validation](#validation) for more information.

**Note:** The line feed (U+000A) and carriage return (U+000D) characters are not permitted in a `password` value. When setting the value of a password control, line feed and carriage return characters are stripped out of the value.

Additional attributes
---------------------

In addition to the attributes that operate on all [`<input>`](../input) elements regardless of their type, password field inputs support the following attributes:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>maxlength</code></td><td>The maximum length the value may be, in UTF-16 characters</td></tr><tr class="even"><td><code>minlength</code></td><td>The minimum length in characters that will be considered valid</td></tr><tr class="odd"><td><code>pattern</code></td><td>A regular expression the value must match in order to be valid</td></tr><tr class="even"><td><code>placeholder</code></td><td>An example value to display in the field when the field is empty</td></tr><tr class="odd"><td><code>readonly</code></td><td>A Boolean attribute which, if present, indicates that the field's contents should not be editable</td></tr><tr class="even"><td><code>size</code></td><td>The number of characters wide the input field should be</td></tr></tbody></table>

### `maxlength`

The maximum number of characters (as UTF-16 code units) the user can enter into the password field. This must be an integer value 0 or higher. If no `maxlength` is specified, or an invalid value is specified, the password field has no maximum length. This value must also be greater than or equal to the value of `minlength`.

The input will fail [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) if the length of the text entered into the field is greater than `maxlength` UTF-16 code units long.

### `minlength`

The minimum number of characters (as UTF-16 code units) the user can enter into the password entry field. This must be an non-negative integer value smaller than or equal to the value specified by `maxlength`. If no `minlength` is specified, or an invalid value is specified, the password input has no minimum length.

The input will fail [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) if the length of the text entered into the field is fewer than `minlength` UTF-16 code units long.

### `pattern`

The `pattern` attribute, when specified, is a regular expression that the input's [`value`](../../global_attributes#attr-value) must match in order for the value to pass [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). It must be a valid JavaScript regular expression, as used by the [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) type, and as documented in our [guide on regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions); the `'u'` flag is specified when compiling the regular expression, so that the pattern is treated as a sequence of Unicode code points, instead of as ASCII. No forward slashes should be specified around the pattern text.

If the specified pattern is not specified or is invalid, no regular expression is applied and this attribute is ignored completely.

**Tip:** Use the [`title`](../input#attr-title) attribute to specify text that most browsers will display as a tooltip to explain what the requirements are to match the pattern. You should also include other explanatory text nearby.

Use of a pattern is strongly recommended for password inputs, in order to help ensure that valid passwords using a wide assortment of character classes are selected and used by your users. With a pattern, you can mandate case rules, require the use of some number of digits and/or punctuation characters, and so forth. See the section [Validation](#validation) for details and an example.

### `placeholder`

The `placeholder` attribute is a string that provides a brief hint to the user as to what kind of information is expected in the field. It should be a word or short phrase that demonstrates the expected type of data, rather than an explanatory message. The text *must not* include carriage returns or line feeds.

If the control's content has one directionality ([LTR](https://developer.mozilla.org/en-US/docs/Glossary/ltr) or [RTL](https://developer.mozilla.org/en-US/docs/Glossary/rtl)) but needs to present the placeholder in the opposite directionality, you can use Unicode bidirectional algorithm formatting characters to override directionality within the placeholder; see [Overriding BiDi using Unicode control characters](https://developer.mozilla.org/en-US/docs/Web/Guide/Unicode_Bidrectional_Text_Algorithm#overriding_bidi_using_unicode_control_characters) in [The Unicode Bidirectional Text Algorithm](https://developer.mozilla.org/en-US/docs/Web/Guide/Unicode_Bidrectional_Text_Algorithm) for those characters.

**Note:** Avoid using the `placeholder` attribute if you can. It is not as semantically useful as other ways to explain your form, and can cause unexpected technical issues with your content. See [Labels and placeholders](../input#labels_and_placeholders) in [&lt;input&gt;: The Input (Form Input) element](../input) for more information.

### `readonly`

A Boolean attribute which, if present, means this field cannot be edited by the user. Its `value` can, however, still be changed from JavaScript code that directly sets the value of the <span class="page-not-created">`HTMLInputElement.value`</span> property.

**Note:** Because a read-only field cannot have a value, `required` does not have any effect on inputs with the `readonly` attribute also specified.

### `size`

The `size` attribute is a numeric value indicating how many characters wide the input field should be. The value must be a number greater than zero, and the default value is 20. Since character widths vary, this may or may not be exact and should not be relied upon to be so; the resulting input may be narrower or wider than the specified number of characters, depending on the characters and the font ([`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) settings in use).

This does *not* set a limit on how many characters the user can enter into the field. It only specifies approximately how many can be seen at a time. To set an upper limit on the length of the input data, use the `maxlength` attribute.

Using password inputs
---------------------

Password input boxes generally work just like other textual input boxes; the main difference is the obscuring of the content to prevent people near the user from reading the password.

### A simple password input

Here we see the most basic password input, with a label established using the [`<label>`](../label) element.

    <label for="userPassword">Password: </label>
    <input id="userPassword" type="password">

### Allowing autocomplete

To allow the user's password manager to automatically enter the password, specify the [`autocomplete`](../input#attr-autocomplete) attribute. For passwords, this should typically be one of the following:

`on`  
Allow the browser or a password manager to automatically fill out the password field. This isn't as informative as using either `current-password` or `new-password`.

`off`  
Don't allow the browser or password manager to automatically fill out the password field. Note that some software ignores this value, since it's typically harmful to users' ability to maintain safe password practices.

`current-password`  
Allow the browser or password manager to enter the current password for the site. This provides more information than `on` does, since it lets the browser or password manager automatically enter currently-known password for the site in the field, but not to suggest a new one.

`new-password`  
Allow the browser or password manager to automatically enter a new password for the site; this is used on "change your password" and "new user" forms, on the field asking the user for a new password. The new password may be generated in a variety of ways, depending on the password manager in use. It may fill in a new suggested password, or it might show the user an interface for creating one.

<!-- -->

    <label for="userPassword">Password:</label>
    <input id="userPassword" type="password" autocomplete="current-password">

### Making the password mandatory

To tell the user's browser that the password field must have a valid value before the form can be submitted, specify the Boolean [`required`](../input#attr-required) attribute.

    <label for="userPassword">Password: </label>
    <input id="userPassword" type="password" required>
    <input type="submit" value="Submit">

### Specifying an input mode

If your recommended (or required) password syntax rules would benefit from an alternate text entry interface than the standard keyboard, you can use the [`inputmode`](../input#attr-inputmode) attribute to request a specific one. The most obvious use case for this is if the password is required to be numeric (such as a PIN). Mobile devices with virtual keyboards, for example, may opt to switch to a numeric keypad layout instead of a full keyboard, to make entering the password easier. If the PIN is for one-time use, set the [`autocomplete`](../input#attr-autocomplete) attribute to either `off` or `one-time-code` to suggest that it's not saved.

    <label for="pin">PIN: </label>
    <input id="pin" type="password" inputmode="numeric">

### Setting length requirements

As usual, you can use the [`minlength`](../input#attr-minlength) and [`maxlength`](../input#attr-maxlength) attributes to establish minimum and maximum acceptable lengths for the password. This example expands on the previous one by specifying that the user's PIN must be at least four and no more than eight digits. The [`size`](../input#attr-size) attribute is used to ensure that the password entry control is eight characters wide.

    <label for="pin">PIN:</label>
    <input id="pin" type="password" inputmode="numeric" minlength="4"
           maxlength="8" size="8">

### Selecting text

As with other textual entry controls, you can use the [`select()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select) method to select all the text in the password field.

#### HTML

    <label for="userPassword">Password: </label>
    <input id="userPassword" type="password" size="12">
    <button id="selectAll">Select All</button>

#### JavaScript

    document.getElementById("selectAll").onclick = function() {
      document.getElementById("userPassword").select();
    }

#### Result

You can also use <span class="page-not-created">`selectionStart`</span> and <span class="page-not-created">`selectionEnd`</span> to get (or set) what range of characters in the control are currently selected, and <span class="page-not-created">`selectionDirection`</span> to know which direction selection occurred in (or will be extended in, depending on your platform; see its documentation for an explanation). However, given that the text is obscured, the usefulness of these is somewhat limited.

Validation
----------

If your application has character set restrictions or any other requirement for the actual content of the entered password, you can use the [`pattern`](../input#attr-pattern) attribute to establish a regular expression to be used to automatically ensure that your passwords meet those requirements.

In this example, only values consisting of at least four and no more than eight hexadecimal digits are valid.

    <label for="hexId">Hex ID: </label>
    <input id="hexId" type="password" pattern="[0-9a-fA-F]{4,8}"
           title="Enter an ID consisting of 4-8 hexadecimal digits"
           autocomplete="new-password">

`disabled`  
This Boolean attribute indicates that the password field is not available for interaction. Additionally, disabled field values aren't submitted with the form.

Examples
--------

### Requesting a Social Security number

This example only accepts input which matches the format for a [valid United States Social Security Number](https://en.wikipedia.org/wiki/Social_Security_number#Structure). These numbers, used for tax and identification purposes in the US, are in the form "123-45-6789". Assorted rules for what values are permitted in each group exist as well.

#### HTML

    <label for="ssn">SSN:</label>
    <input type="password" id="ssn" inputmode="numeric" minlength="9" maxlength="12"
        pattern="(?!000)([0-6]\d{2}|7([0-6]\d|7[012]))([ -])?(?!00)\d\d\3(?!0000)\d{4}"
        required autocomplete="off">
    <br>
    <label for="ssn">Value:</label>
    <span id="current"></span>

This uses a [`pattern`](../input#attr-pattern) which limits the entered value to strings representing legal Social Security numbers. Obviously, this regexp doesn't guarantee a valid SSN (since we don't have access to the Social Security Administration's database), but it does ensure the number could be one; it generally avoids values that cannot be valid. In addition, it allows the three groups of digits to be separated by a space, a dash ("-"), or nothing.

The [`inputmode`](../input#attr-inputmode) is set to `numeric` to encourage devices with virtual keyboards to switch to a numeric keypad layout for easier entry. The [`minlength`](../input#attr-minlength) and [`maxlength`](../input#attr-maxlength) attributes are set to 9 and 12, respectively, to require that the value be at least nine and no more than 12 characters (the former without separating characters between the groups of digits and the latter with them). The [`required`](../input#attr-required) attribute is used to indicate that this control must have a value. Finally, [`autocomplete`](../input#attr-autocomplete) is set to `off` to avoid password managers and session restore features trying to set its value, since this isn't a password at all.

#### JavaScript

This is just some simple code to display the entered SSN onscreen so you can see it. Obviously this defeats the purpose of a password field, but it's helpful for experimenting with the `pattern`.

    var ssn = document.getElementById("ssn");
    var current = document.getElementById("current");

    ssn.oninput = function(event) {
      current.textContent = ssn.value;
    }

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#password-state-(type=password)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="password"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#password-state-typepassword">HTML 5.1<br />
<span class="small">The definition of '&lt;input type="password"&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`password`

1

12

1

2

2

1

?

Yes

4

Yes

Yes

Yes

`insecure_login_handling`

No

No

52

No

No

No

No

No

52

No

No

No

See also
--------

-   [Compatibility of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/password" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/password</a>
