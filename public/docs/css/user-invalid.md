# :user-invalid (:-moz-ui-invalid)

The `:user-invalid` CSS [pseudo-class](pseudo-classes) represents any validated form element whose value isn't valid based on their [validation constraints](https://developer.mozilla.org/en-US/docs/Learn/Forms#constraint_validation), after the user has interacted with it.

The `:user-invalid` pseudo-class must match an [`:invalid`](:invalid), [`:out-of-range`](:out-of-range), or blank-but [`:required`](:required) element between the time the user has attempted to submit the form and before the user has interacted again with the form element.

**Note**

The pseudo-class behaves in the same way as the non-standard `:-moz-ui-invalid` pseudo-class.

## Syntax

    :user-invalid

## Examples

### Setting a color and symbol on :user-invalid

In the following example, the red border and <span style="color:red">X</span> only display once the user has interacted with the field. Try typing something other than an email address to see it in action.

    <form>
      <label for="email">Email *: </label>
      <input id="email" name="email" type="email" required>
      <span></span>
    </form>

    input:user-invalid {
      border: 2px solid red;
    }

    input:user-invalid + span::before {
      content: '✖';
      color: red;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#user-invalid-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':user-invalid' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds :user-invalid</td></tr></tbody></table>

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

`:user-invalid`

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
- [`:user-valid`](:user-valid)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:user-invalid" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:user-invalid</a>
