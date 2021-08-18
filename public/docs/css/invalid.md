# :invalid

The `:invalid` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents any [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) or other [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element whose contents fail to [validate](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation).

    /* Selects any invalid <input> */
    input:invalid {
      background-color: pink;
    }

This pseudo-class is useful for highlighting field errors for the user.

## Syntax

    :invalid

## Examples

### A form that colors elements green when they validate and red when they don't.

#### HTML

    <form>
      <div class="field">
        <label for="url_input">Enter a URL:</label>
        <input type="url" id="url_input">
      </div>

      <div class="field">
        <label for="email_input">Enter an email address:</label>
        <input type="email" id="email_input" required>
      </div>
    </form>

#### CSS

    label {
      display: block;
      margin: 1px;
      padding: 1px;
    }

    .field {
      margin: 1px;
      padding: 1px;
    }

    input:invalid {
      background-color: #ffdddd;
    }

    form:invalid {
      border: 5px solid #ffdddd;
    }

    input:valid {
      background-color: #ddffdd;
    }

    form:valid {
      border: 5px solid #ddffdd;
    }

    input:required {
      border-color: #800000;
      border-width: 3px;
    }

    input:required:invalid {
      border-color: #c00000;
    }

#### Result

## Accessibility concerns

The color red is commonly used to indicate invalid input. People who have certain types of color blindness will be unable to determine the input's state unless it is accompanied by an additional indicator that does not rely on color to convey meaning. Typically, descriptive text and/or an icon are used.

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-without-color.html)

## Notes

### Radio buttons

If any one of the radio buttons in a group is `required`, the `:invalid` pseudo-class is applied to all of them if none of the buttons in the group is selected. (Grouped radio buttons share the same value for their `name` attribute.)

### Gecko defaults

By default, Gecko does not apply a style to the `:invalid` pseudo-class. However, it does apply a style (a red "glow" using the [`box-shadow`](box-shadow) property) to the [`:user-invalid`](:user-invalid) pseudo-class, which applies in a subset of cases for `:invalid`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#selector-invalid">HTML Living Standard<br />
<span class="small">The definition of ':invalid' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/#selector-invalid">HTML5<br />
<span class="small">The definition of ':invalid' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines the semantics of HTML and constraint validation.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#validity-pseudos">Selectors Level 4<br />
<span class="small">The definition of ':invalid' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`:invalid`

10

12

4

10

10

5

37

18

4

10.1

5

1.0

`form`

40

79

13

No

27

9

40

40

14

27

9

4.0

## See also

- Other validation-related pseudo-classes: [`:required`](:required), [`:optional`](:optional), [`:valid`](:valid)
- Related Mozilla pseudo-classes: [`:user-invalid`](:user-invalid), [`:-moz-submit-invalid`](:-moz-submit-invalid)
- [Form data validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
- Accessing the [validity state](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState) from JavaScript

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid</a>
