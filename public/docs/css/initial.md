# initial

The `initial` CSS keyword applies the [initial (or default) value](initial_value) of a property to an element. It can be applied to any CSS property. This includes the CSS shorthand [`all`](all), with which `initial` can be used to restore all CSS properties to their initial state.

On [inherited properties](inheritance#inherited_properties), the initial value may be unexpected. You should consider using the [`inherit`](inherit), [`unset`](unset), or [`revert`](revert) keywords instead.

## Examples

### Using initial to reset color for an element

#### HTML

    <p>
      <span>This text is red.</span>
      <em>This text is in the initial color (typically black).</em>
      <span>This is red again.</span>
    </p>

#### CSS

    p {
      color: red;
    }

    em {
      color: initial;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-cascade/#initial">CSS Cascading and Inheritance Level 4<br />
<span class="small">The definition of 'initial' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No changes from Level 3.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-cascade-3/#initial">CSS Cascading and Inheritance Level 3<br />
<span class="small">The definition of 'initial' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`initial`

1

13

19

1-24

No

15

1.2

1

18

19

4-24

14

1

1.0

## See also

- Use [`unset`](unset) to set a property to its inherited value if it inherits, or to its initial value if not.
- Use [`revert`](revert) to reset a property to the value established by the user-agent stylesheet (or by user styles, if any exist).
- Use [`inherit`](inherit) to make an element's property the same as its parent.
- The [`all`](all) property lets you reset all properties to their initial, inherited, reverted, or unset state at once.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/initial" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/initial</a>
