# &lt;time-percentage&gt;

The `<time-percentage>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a value that can be either a [`<time>`](time) or a [`<percentage>`](percentage).

## Syntax

Refer to the documentation for [`<time>`](time) and [`<percentage>`](percentage) for details of the individual syntaxes allowed by this type.

## Examples

### Use in calc()

Where a `<time-percentage>` is specified as an allowable type, this means that the percentage resolves to a time and therefore can be used in a [`calc()`](<calc()>) expression.

### Valid percentages

    50%
    +50%        Optional plus sign
    -50%        Negative percentages are not valid for all properties that accept percentages

### Invalid percentages

    50 %        Space not allowed between the space and the percentage sign

### Valid times

    12s         Positive integer
    -456ms      Negative integer
    4.3ms       Non-integer
    14mS        The unit is case-insensitive, although capital letters are not recommended.
    +0s         Zero with a leading + and a unit
    -0ms        Zero with a leading - and a unit

### Invalid times

    0           Although unitless zero is allowed for <length>s, it's invalid for <time>s.
    12.0        This is a <number>, not a <time>, because it's missing a unit.
    7 ms        No space is allowed between the number and the unit.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#mixed-percentages">CSS Values and Units Module Level 4<br />
<span class="small">The definition of '&lt;time-percentage&gt;' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#mixed-percentages">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '&lt;time-percentage&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines <code>&lt;time-percentage&gt;</code>. Adds <code>calc()</code></td></tr></tbody></table>

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

`time-percentage`

1

12

4

9

10.1

3.1

2

18

4

10.1

2

1.0

## See also

- [`<percentage>`](percentage)
- [`<time>`](time)
- [CSS Values and Units](css_values_and_units)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/time-percentage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/time-percentage</a>
