# &lt;time&gt;

The `<time>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a time value expressed in seconds or milliseconds. It is used in [`animation`](animation), [`transition`](transition), and related properties.

## Syntax

The `<time>` data type consists of a [`<number>`](number) followed by one of the units listed below. Optionally, it may be preceded by a single `+` or `-` sign. As with all dimensions, there is no space between the unit literal and the number.

**Note:** Although the number `0` is always the same regardless of unit, the unit may not be omitted. In other words, `0` is invalid and does not represent `0s` or `0ms`.

### Units

`s`  
Represents a time in seconds. Examples: `0s`, `1.5s`, `-60s`.

`ms`  
Represents a time in milliseconds. Examples: `0ms`, `150.25ms`, `-60000ms`.

**Note:** Conversion between `s` and `ms` follows the logical `1s` = `1000ms`.

## Examples

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#time">CSS Values and Units Module Level 4<br />
<span class="small">The definition of '&lt;time&gt;' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#time">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '&lt;time&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Normative definition of <code>s</code> and <code>ms</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/aural.html#times">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '&lt;time&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Informal definition of <code>s</code> and <code>ms</code>.</td></tr></tbody></table>

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

`time`

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

- [`<time-percentage>`](time-percentage)
- [CSS Values and Units](css_values_and_units)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/time" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/time</a>
