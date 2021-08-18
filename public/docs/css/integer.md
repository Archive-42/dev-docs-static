# &lt;integer&gt;

The `<integer>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) is a special type of [`<number>`](number) that represents a whole number, whether positive or negative. Integers can be used in numerous CSS properties, such as [`column-count`](column-count), [`counter-increment`](counter-increment), [`grid-column`](grid-column), [`grid-row`](grid-row), and [`z-index`](z-index).

## Syntax

The `<integer>` data type consists of one or several decimal digits, 0 through 9 inclusive, optionally preceded by a single `+` or `-` sign. There is no unit associated with integers.

**Note:** There is no official range of valid `<integer>` values. Opera 12.1 supports values up to 2<sup>15</sup>-1, IE up to 2<sup>20</sup>-1, and other browsers even higher. During the CSS3 Values cycle there was a lot of discussion about setting a minimum range to support: the latest decision, [in April 2012 during the LC phase](https://lists.w3.org/Archives/Public/www-style/2012Apr/0633.html), was \[-2<sup>27</sup>-1; 2<sup>27</sup>-1\], but other values like 2<sup>24</sup>-1 and 2<sup>30</sup>-1 [were also proposed](https://lists.w3.org/Archives/Public/www-style/2012Apr/0530.html). However, the latest spec doesn't specify a range anymore.

## Interpolation

When animated, values of the `<integer>` data type are interpolated using discrete, whole steps. The calculation is done as if they were real, floating-point numbers; the discrete value is obtained using the [floor function](https://en.wikipedia.org/wiki/Floor_function). The speed of the interpolation is determined by the [timing function](easing-function) associated with the animation.

## Examples

### Valid integers

    12          Positive integer (without a leading + sign)
    +123        Positive integer (with a leading + sign)
    -456        Negative integer
    0           Zero
    +0          Zero, with a leading +
    -0          Zero, with a leading -

### Invalid integers

    12.0        This is a <number>, not an <integer>, though it represents an integer.
    12.         Decimal points are not allowed.
    +---12      Only one leading +/- is allowed.
    ten         Letters are not allowed.
    _5          Special characters are not allowed.
    \35         Escaped Unicode characters are not allowed, even if they are an integer (here: 5).
    \4E94       Non-arabic numerals are not allowed, even when escaped (here: the Japanese 5, 五).
    3e4         Scientific notation is not allowed.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#integers">CSS Values and Units Module Level 4<br />
<span class="small">The definition of '&lt;integer&gt;' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>No significant change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#integers">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '&lt;integer&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No significant change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/syndata.html#numbers">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '&lt;integer&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Explicit definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/">CSS Level 1<br />
<span class="small">The definition of '&lt;integer&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Implicit definition.</td></tr></tbody></table>

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

`integer`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

## See also

- [`<number>`](number)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/integer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/integer</a>
