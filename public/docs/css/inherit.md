# inherit

The `inherit` CSS keyword causes the element for which it is specified to take the [computed value](computed_value) of the property from its parent element. It can be applied to any CSS property, including the CSS shorthand [`all`](all).

For [inherited properties](inheritance#inherited_properties), this reinforces the default behavior, and is only needed to override another rule. For [non-inherited properties](inheritance#non-inherited_properties), this specifies a behavior that typically makes relatively little sense and you may consider using [`initial`](initial) instead, or [`unset`](unset) on the [`all`](all) property.

Inheritance is always from the parent element in the document tree, even when the parent element is not the containing block.

## Examples

### Exclude selected elements from a rule

    /* Make second-level headers green */
    h2 { color: green; }

    /* ...but leave those in the sidebar alone so they use their parent's color */
    #sidebar h2 { color: inherit; }

In this example the `h2` elements inside the sidebar might be different colors. For example, if one of them were the child of a div matched by the rule ...

    div#current { color: blue; }

... it would be blue.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-cascade/#inherit">CSS Cascading and Inheritance Level 4<br />
<span class="small">The definition of 'inherit' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No changes from Level 3.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#common-keywords">CSS Values and Units Module Level 3<br />
<span class="small">The definition of 'inherit' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No significant change from <a href="https://www.w3.org/TR/CSS2/">CSS Level 2 (Revision 1)</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/cascade.html#value-def-inherit">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'inherit' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`inherit`

1

12

1

8

4

1

1

18

4

14

1

1.0

## See also

- <a href="inheritance" class="internal">Inheritance</a>
- Use [`initial`](initial) to set a property to its initial value.
- Use [`unset`](unset) to set a property to its inherited value if it inherits, or to its initial value if not.
- Use [`revert`](revert) to reset a property to the value established by the user-agent stylesheet (or by user styles, if any exist).
- The [`all`](all) property lets you reset all properties to their initial, inherited, reverted, or unset state at once.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/inherit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/inherit</a>
