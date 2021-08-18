# unset

The `unset` CSS keyword resets a property to its inherited value if the property naturally inherits from its parent, and to its [initial value](initial_value) if not. In other words, it behaves like the [`inherit`](inherit) keyword in the first case, when the property is an [inherited property](inheritance#inherited_properties), and like the [`initial`](initial) keyword in the second case, when the property is a [non-inherited property](inheritance#non-inherited_properties).

`unset` can be applied to any CSS property, including the CSS shorthand [`all`](all).

## Examples

### Color

#### HTML

    <p>This text is red.</p>
    <div class="foo">
      <p>This text is also red.</p>
    </div>
    <div class="bar">
      <p>This text is green (default inherited value).</p>
    </div>

#### CSS

    .foo {
      color: blue;
    }
    .bar {
      color: green;
    }

    p {
      color: red;
    }
    .bar p {
      color: unset;
    }

#### Result

### Border

#### HTML

    <p>This text has a red border.</p>
    <div>
      <p>This text has a red border.</p>
    </div>
    <div class="bar">
      <p>This text has a black border (initial default, not inherited).</p>
    </div>

#### CSS

    div {
      border: 1px solid green;
    }

    p {
      border: 1px solid red;
    }

    .bar p {
      border-color: unset;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-cascade/#inherit-initial">CSS Cascading and Inheritance Level 4<br />
<span class="small">The definition of 'unset' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No changes from Level 3.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-cascade-3/#inherit-initial">CSS Cascading and Inheritance Level 3<br />
<span class="small">The definition of 'unset' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`unset`

41

13

27

No

28

9.1

41

41

27

28

9.3

4.0

## See also

- Use [`initial`](initial) to set a property to its initial value.
- Use [`revert`](revert) to reset a property to the value established by the user-agent stylesheet (or by user styles, if any exist).
- Use [`inherit`](inherit) to make an element's property the same as its parent.
- The [`all`](all) property lets you reset all properties to their initial, inherited, reverted, or unset state at once.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/unset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/unset</a>
