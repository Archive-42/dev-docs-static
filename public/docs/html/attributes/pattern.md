HTML attribute: pattern
=======================

The `pattern` attribute specifies a [regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) the form control's value should match. If a non-`null` value doesn't conform to the constraints set by the `pattern` value, the [`ValidityState`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState) object's read-only [`patternMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/patternMismatch) property will be true.

The `pattern` attribute is an attribute of the [text](../element/input/text), [tel](../element/input/tel), [email](../element/input/email), [url](../element/input/url), [password](../element/input/password), and [search](../element/input/search) input types.

The `pattern` attribute, when specified, is a regular expression which the input's [`value`](../global_attributes#attr-value) must match in order for the value to pass [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). It must be a valid JavaScript regular expression, as used by the [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) type, and as documented in our [guide on regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions); the `'u'` flag is specified when compiling the regular expression, so that the pattern is treated as a sequence of Unicode code points, instead of as ASCII. No forward slashes should be specified around the pattern text.

If the specified pattern is not specified or is invalid, no regular expression is applied and this attribute is ignored.

**Tip:** Use the [`title`](../element/input#attr-title) attribute to specify text that most browsers will display as a tooltip to explain what the requirements are to match the pattern. You **must not** rely on the tooltip alone for an explanation. See below for more information on usability.

Some of the input types supporting the pattern attribute, notably the [email](../element/input/email) and [url](../element/input/url) input types, have expected value syntaxes that must be matched. If the pattern attribute isn't present, and the value doesn't match the expected syntax for that value type, the [`ValidityState`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState) object's read-only [`typeMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/typeMismatch) property will be true.

### Usability

When including a `pattern`, provide a description of the pattern in visible text near the control. Additionally, include a `title` attribute which gives a description of the pattern. User agents may use the title contents during constraint validation to tell the user that the pattern is not matched. Some browsers show a tooltip with title contents, improving usability for sighted users. Additionally, assistive technology may read the title aloud when the control gains focus, but this should not be relied upon for accessibility.

### Constraint validation

If the input’s value is not the empty string and the value does not match the entire regular expression, there is a from a [`patternMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/patternMismatch).  
The pattern's regular expression, when matched against the value, must have its start anchored to the start of the string and its end anchored to the end of the string, which is slightly different from JavaScript regular expressions: in the case of pattern attribute, we are matching against the entire value, not just any subset, as if a `^(?:` were implied at the start of the pattern and `)$` at the end.

Examples
--------

Given the following:

    <p>
     <label>Enter your phone number in the format (123)456-7890
      (<input name="tel1" type="tel" pattern="[0-9]{3}" placeholder="###" aria-label="3-digit area code" size="2"/>)-
       <input name="tel2" type="tel" pattern="[0-9]{3}" placeholder="###" aria-label="3-digit prefix" size="2"/> -
       <input name="tel3" type="tel" pattern="[0-9]{4}" placeholder="####" aria-label="4-digit number" size="3"/>
     </label>
    </p>

Here we have 3 sections for a north American phone number with an implicit label encompassing all three components of the phone number, expecting 3-digits, 3-digits and 4-digits respectively, as defined by the `pattern` attribute set on each.

If the values are too long or too short, or contain characters that aren't digits, the patternMismatch will be true. When `true`, the element matches the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) CSS pseudo-classes.

    input:invalid {
      border: red solid 3px;
    }

Had we used `minlength` and `maxlength` attributes instead, we may have seen [`validityState.tooLong`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooLong) or [`validityState.tooShort`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooShort) being true.

### Specifying a pattern

You can use the [`pattern`](../element/input#attr-pattern) attribute to specify a regular expression that the inputted value must match in order to be considered valid (see [Validating against a regular expression](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#validating_against_a_regular_expression) for a simple crash course on using regular expressions to validate inputs).

The example below restricts the value to 4-8 characters and requires that it contain only lower-case letters.

    <form>
      <div>
        <label for="uname">Choose a username: </label>
        <input type="text" id="uname" name="name" required size="45"
               pattern="[a-z]{4,8}" title="4 to 8 lowercase letters">
        <span class="validity"></span>
        <p>Usernames must be lowercase and 4-8 characters in length.</p>
      </div>
      <div>
        <button>Submit</button>
      </div>
    </form>

This renders like so:

### Accessibility Concerns

When a control has a `pattern` attribute, the `title` attribute, if used, must describe the pattern. Relying on the `title` attribute for the visual display of text content is generally discouraged as many user agents do not expose the attribute in an accessible manner. Some browsers show a tooltip when an element with a title is hovered, but that leaves out keyboard-only and touch-only users. This is one of the several reasons you must include information informing users how to fill out the control to match the requirements.

While `title`s are used by some browsers to populate error messaging, because browsers sometimes also show the title as text on hover, it therefore shows in non-error situations, so be careful not to word titles as if an error has occurred.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#attr-input-pattern">HTML Living Standard<br />
<span class="small">The definition of 'pattern' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/forms.html#attr-input-pattern">HTML 5.1<br />
<span class="small">The definition of 'pattern' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/forms.html#attr-input-pattern">HTML5<br />
<span class="small">The definition of 'pattern' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `html.elements.attributes.pattern`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [Constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation)
-   [Forms: Data form validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
-   [Regular Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern</a>
