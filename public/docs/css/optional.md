# :optional

The `:optional` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents any [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element that does not have the [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-required) attribute set on it.

    /* Selects any optional <input> */
    input:optional {
      border: 1px dashed black;
    }

This pseudo-class is useful for styling fields that are not required to submit a form.

**Note:** The [`:required`](:required) pseudo-class selects _required_ form fields.

## Syntax

    :optional

## Examples

### The optional field has a purple border

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

    input:optional {
      border-color: rebeccapurple;
      border-width: 3px;
    }

#### Result

## Accessibility concerns

If a [form](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) contains optional [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)s, required inputs should be indicated using the [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-required) attribute. This will ensure that people navigating with the aid of assistive technology such as a screen reader will be able to understand which inputs need valid content to ensure a successful form submission.

Required inputs should also be indicated visually, using a treatment that does not rely solely on color to convey meaning. Typically, descriptive text and/or an icon are used.

- [MDN Understanding WCAG, Guideline 3.3 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Understandable#guideline_3.3_%e2%80%94_input_assistance_help_users_avoid_and_correct_mistakes)
- [Understanding Success Criterion 3.3.2 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/minimize-error-cues.html)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#selector-optional">HTML Living Standard<br />
<span class="small">The definition of ':optional' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/#selector-optional">HTML5<br />
<span class="small">The definition of ':optional' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines the semantics of HTML and constraint validation.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#opt-pseudos">Selectors Level 4<br />
<span class="small">The definition of ':optional' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr></tbody></table>

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

`:optional`

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

## See also

- Other validation-related pseudo-classes: [`:required`](:required), [`:invalid`](:invalid), [`:valid`](:valid)
- [Form data validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:optional" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:optional</a>
