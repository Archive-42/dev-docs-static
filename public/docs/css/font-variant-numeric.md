# font-variant-numeric

The `font-variant-numeric` CSS property controls the usage of alternate glyphs for numbers, fractions, and ordinal markers.

## Syntax

    font-variant-numeric: normal;
    font-variant-numeric: ordinal;
    font-variant-numeric: slashed-zero;
    font-variant-numeric: lining-nums;         /* <numeric-figure-values> */
    font-variant-numeric: oldstyle-nums;       /* <numeric-figure-values> */
    font-variant-numeric: proportional-nums;   /* <numeric-spacing-values> */
    font-variant-numeric: tabular-nums;        /* <numeric-spacing-values> */
    font-variant-numeric: diagonal-fractions;  /* <numeric-fraction-values> */
    font-variant-numeric: stacked-fractions;   /* <numeric-fraction-values> */
    font-variant-numeric: oldstyle-nums stacked-fractions;

    /* Global values */
    font-variant-numeric: inherit;
    font-variant-numeric: initial;
    font-variant-numeric: unset;

This property can take one of two forms:

- either the keyword value `normal`
- or one or more of the other values listed below, space-separated, in any order.

### Values

`normal`  
This keyword leads to the deactivation of the use of such alternate glyphs.

`ordinal`  
This keyword forces the use of special glyphs for the ordinal markers, like 1<sup>st</sup>, 2<sup>nd</sup>, 3<sup>rd</sup>, 4<sup>th</sup> in English or a 1<sup>a</sup> in Italian. It corresponds to the OpenType values `ordn`.

`slashed-zero`  
This keyword forces the use of a 0 with a slash; this is useful when a clear distinction between O and 0 is needed. It corresponds to the OpenType values `zero`.

_&lt;numeric-figure-values_&gt;  
These values control the figures used for numbers. Two values are possible:

- `lining-nums` activating the set of figures where numbers are all lying on the baseline. It corresponds to the OpenType values `lnum`.
- `oldstyle-nums` activating the set of figures where some numbers, like 3, 4, 7, 9 have descenders. It corresponds to the OpenType values `onum`.

_&lt;numeric-spacing-values_&gt;  
These values controls the sizing of figures used for numbers. Two values are possible:

- `proportional-nums` activating the set of figures where numbers are not all of the same size. It corresponds to the OpenType values `pnum`.
- `tabular-nums` activating the set of figures where numbers are all of the same size, allowing them to be easily aligned like in tables. It corresponds to the OpenType values `tnum`.

_&lt;numeric-fraction-values_&gt;  
These values controls the glyphs used to display fractions. Two values are possible:

- `diagonal-fractions` activating the set of figures where the numerator and denominator are made smaller and separated by a slash. It corresponds to the OpenType values `frac`.
- `stacked-fractions` activating the set of figures where the numerator and denominator are made smaller, stacked and separated by a horizontal line. It corresponds to the OpenType values `afrc`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | [ <numeric-figure-values> || <numeric-spacing-values> || <numeric-fraction-values> || ordinal || slashed-zero ]where
    <numeric-figure-values> = [ lining-nums | oldstyle-nums ]
    <numeric-spacing-values> = [ proportional-nums | tabular-nums ]
    <numeric-fraction-values> = [ diagonal-fractions | stacked-fractions ]

## Examples

### Setting ordinal numeric forms

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-3/#propdef-font-variant-numeric">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-variant-numeric' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`font-variant-numeric`

52

79

34

No

39

9.1

52

52

34

41

9.3

6.0

## See Also

- [`font-variant-alternates`](font-variant-alternates)
- [`font-variant-caps`](font-variant-caps)
- [`font-variant-east-asian`](font-variant-east-asian)
- [`font-variant-ligatures`](font-variant-ligatures)
- [`font-variant`](font-variant)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-numeric" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-numeric</a>
