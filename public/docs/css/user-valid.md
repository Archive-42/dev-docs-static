# :user-valid (:-moz-ui-valid)

The `:user-valid` CSS [pseudo-class](pseudo-classes) represents any validated form element whose value validates correctly based on its [validation constraints](https://developer.mozilla.org/en-US/docs/Learn/Forms#constraint_validation). However, unlike [`:valid`](:valid) it only matches once the user has interacted with it.

**Note**

The pseudo-class behaves in the same way as the non-standard `:-moz-ui-valid` pseudo-class.

This pseudo-class is applied according to the following rules:

- If the control does not have focus, and the value is valid, apply this pseudo-class.
- If the control has focus, and the value was valid (including empty) when it gained focus, apply this pseudo-class.
- If the control has focus, and the value was invalid when it gained focus, re-validate on every keystroke.
- If the element is required, the preceding rules apply only if the user has changed the value or attempted to submit the form.

The result is that if the control was valid when the user started interacting with it, the validity styling is changed only when the user shifts focus to another control. However, if the user is trying to correct a previously-flagged value, the control shows immediately when the value becomes valid. Required items are flagged as invalid only if the user changes them or attempts to submit an unchanged invalid value.

## Syntax

    :user-valid

## Examples

### Setting a color and symbol on :user-valid

In the following example, the green border and <span style="color:green">✓</span> only display once the user has interacted with the field. Try changing the email address to another valid email to see it in action.

    <form>
      <label for="email">Email *: </label>
      <input id="email" name="email" type="email" value="test@example.com" required>
      <span></span>
    </form>

    input:user-valid {
      border: 2px solid green;
    }

    input:user-valid + span::before {
      content: '✓';
      color: green;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#user-valid-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':user-valid' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds :user-valid</td></tr></tbody></table>

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

`:user-valid`

No

No

88

4

No

No

No

No

No

88

4

No

No

No

## See also

- [`:valid`](:valid)
- [`:invalid`](:invalid)
- [`:required`](:required)
- [`:optional`](:optional)
- [`:user-invalid`](:user-invalid)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:user-valid" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:user-valid</a>
