# range

When defining custom counter styles, the `range` descriptor lets the author specify a range of counter values over which the style is applied. If a counter value is outside the specified range, then the fallback style will be used to construct the representation of that marker.

## Syntax

    /* Keyword value */
    range: auto;

    /* Range values */
    range: 2 5;
    range: infinite 10;
    range: 6 infinite;
    range: infinite infinite;

    /* Multiple range values */
    range: 2 5, 8 10;
    range: infinite 6, 10 infinite;

### Values

`auto`  
The range depends on the counter system:

- For cyclic, numeric, and fixed systems, the range is negative infinity to positive infinity.
- For alphabetic and symbolic systems, the range is 1 to positive infinity.
- For additive systems, the range is 0 to positive infinity.
- For extends systems, the range is whatever auto would produce for the extended system; if extending a complex predefined style (§7 Complex Predefined Counter Styles), the range is the style’s defined range.

`[ [ | infinite ]{2} ]#`  
Defines a comma-separated list of ranges. For each individual range, the first value is the lower bound and the second value is the upper bound. A range is inclusive, that means it always contains both, the lower and upper bound numbers. If infinite is used as the first value in a range, it represents negative infinity; if it is used as the second value, it represents positive infinity. The range of the counter style is the union of all the ranges defined in the list.  
If the lower bound of any range is higher than the upper bound, the entire descriptor is invalid and will be ignored.

## Description

The value of the range descriptor can be either auto or a comma separated list of lower and upper bounds specified as integers.

If value is auto, then for cyclic, numeric, and fixed system, the range will be from negative infinity to positive infinity. For alphabetic and symbolic systems, range will be from 1 to positive infinity. For additive systems, auto will result in the range 0 to positive infinity. For extends systems, the range is whatever auto will produce for the extended system.

When range is specified as integers, the value `infinite` can be used to denote infinity. If _infinite_ is specified as the first value in a range, then it is interpreted as negative infinity. If used as upper bound, it is taken as positive infinity.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@counter-style"><code>@counter-style</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    [ [ <integer> | infinite ]{2} ]# | auto

## Examples

### Setting counter style over a range

    <ul class="list">
      <li>One</li>
      <li>Two</li>
      <li>Three</li>
      <li>Four</li>
      <li>Five</li>
      <li>Six</li>
      <li>Seven</li>
      <li>Eight</li>
      <li>Nine</li>
      <li>Ten</li>
    </ul>

    @counter-style range-multi-example {
      system: cyclic;
      symbols: "\25A0" "\25A1";
      range: 2 4, 7 9;
    }

    .list {
      list-style: range-multi-example;
    }

The above list will display as follows:

1. One  
   □. Two  
   ■. Three  
   □. Four
2. Five
3. Six  
   ■. Seven  
   □. Eight  
   ■. Nine
4. Ten

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-counter-styles-3/#counter-style-range">CSS Counter Styles Level 3<br />
<span class="small">The definition of 'range' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`range`

No

No

33

No

No

No

No

No

33

No

No

No

## See also

- [`list-style`](../list-style), [`list-style-image`](../list-style-image), [`list-style-position`](../list-style-position)
- [`symbols()`](<../symbols()>), the functional notation creating anonymous counter styles.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/range" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/range</a>
