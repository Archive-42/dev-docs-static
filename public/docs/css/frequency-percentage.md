# &lt;frequency-percentage&gt;

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `<frequency-percentage>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a value that can be either a [`<frequency>`](frequency) or a [`<percentage>`](percentage). Frequency values, e.g. the pitch of a speaking voice, are not currently used in any CSS properties.

## Syntax

The value of a `<frequency-percentage>` is either a [`<frequency>`](frequency) or a [`<percentage>`](percentage); see their individual reference pages for details about their syntaxes.

## Description

### Use in calc()

Where a `<frequency-percentage>` is specified as an allowable type, this means that the percentage resolves to a frequency and therefore can be used in a `calc()` expression.

## Examples

### Valid percentage values

    90% Positive percentage
    +90% Positive percentage with leading +
    -90% Negative percentage — not valid for all properties that use percentages

### Invalid percentage values

    90 % No space is allowed between the number and the unit

### Valid frequency values

    12Hz     Positive integer
    4.3Hz    Non-integer
    14KhZ    The unit is case-insensitive, though non-SI capitalization is not recommended.
    +0Hz     Zero, with a leading + and a unit
    -0kHz    Zero, with a leading - and a unit

### Invalid frequency values

    12.0     This is a <number>, not an <frequency>, because it is missing a unit.
    7 Hz     No space is allowed between the number and the unit.
    0        Although unitless zero is an allowable <length>, it's an invalid <frequency>.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#mixed-percentages">CSS Values and Units Module Level 4<br />
<span class="small">The definition of '&lt;frequency-percentage&gt;' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#mixed-percentages">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '&lt;frequency-percentage&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines <code>&lt;frequency-percentage&gt;</code>. Adds <code>calc()</code></td></tr></tbody></table>

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

`frequency-percentage`

No

No

No

See [bug 741643](https://bugzil.la/741643).

No

No

No

No

No

No

No

No

No

## See also

- [CSS data types](css_types)
- [CSS Values and Units](css_values_and_units)
- Related CSS data types:
  - [`<frequency>`](frequency)
  - [`<percentage>`](percentage)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/frequency-percentage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/frequency-percentage</a>
