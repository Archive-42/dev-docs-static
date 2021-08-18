# &lt;number&gt;

The `<number>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a number, being either an integer or a number with a fractional component.

## Syntax

The syntax of `<number>` extends the syntax of [`<integer>`](integer). A fractional value is represented by a `.` followed by one or more decimal digits, and may be appended to an integer. There is no unit associated with numbers.

## Interpolation

When animated, values of the `<number>` CSS data type are interpolated as real, floating-point numbers. The speed of the interpolation is determined by the [timing function](easing-function) associated with the animation.

## Examples

### Valid numbers

    12          A raw <integer> is also a <number>.
    4.01        Positive fraction
    -456.8      Negative fraction
    0.0         Zero
    +0.0        Zero, with a leading +
    -0.0        Zero, with a leading -
    .60         Fractional number without a leading zero
    10e3        Scientific notation
    -3.4e-2     Complicated scientific notation

### Invalid numbers

    12.         Decimal points must be followed by at least one digit.
    +-12.2      Only one leading +/- is allowed.
    12.1.1      Only one decimal point is allowed.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#numbers">CSS Values and Units Module Level 4<br />
<span class="small">The definition of '&lt;number&gt;' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>No significant change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#numbers">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '&lt;number&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No significant change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/syndata.html#numbers">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '&lt;number&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Explicit definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/">CSS Level 1<br />
<span class="small">The definition of '&lt;number&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Implicit definition.</td></tr></tbody></table>

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

`number`

1

12

1

5

2

1

1

18

4

10.1

1

1.0

`scientific_notation`

43

12

29

11

30

10.1

43

43

29

30

10.3

4.0

## See also

- [`<integer>`](integer)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/number" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/number</a>
