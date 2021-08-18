# min-width

The `min-width` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the minimum width of an element. It prevents the [used value](used_value) of the [`width`](width) property from becoming smaller than the value specified for `min-width`.

The element's width is set to the value of `min-width` whenever `min-width` is larger than [`max-width`](max-width) or [`width`](width).

## Syntax

    /* <length> value */
    min-width: 3.5em;

    /* <percentage> value */
    min-width: 10%;

    /* Keyword values */
    min-width: max-content;
    min-width: min-content;
    min-width: fit-content(20em);

    /* Global values */
    min-width: inherit;
    min-width: initial;
    min-width: unset;

### Values

[`<length>`](length)  
Defines the `min-width` as an absolute value.

[`<percentage>`](percentage)  
Defines the `min-width` as a percentage of the containing block's width.

`auto`  
The browser will calculate and select a `min-width` for the specified element.

`max-content`  
The intrinsic preferred `min-width`.

`min-content`  
The intrinsic minimum `min-width`.

`fit-content(<length-percentage>`)  
Uses the `fit-content` formula with the available space replaced by the specified argument, i.e. `min(max-content, max(min-content, argument))`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements but non-replaced inline elements, table rows, and row groups</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>the percentage as specified or the absolute length</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    auto | <length> | <percentage> | min-content | max-content | fit-content | fit-content(<length-percentage>)where
    <length-percentage> = <length> | <percentage>

## Examples

### Setting minimum element width

    table { min-width: 75%; }

    form { min-width: 0; }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-sizing-4/#width-height-keywords">CSS Box Sizing Module Level 4<br />
<span class="small">The definition of 'min-width' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-sizing-3/#width-height-keywords">CSS Box Sizing Module Level 3<br />
<span class="small">The definition of 'min-width' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the <code>max-content</code>, <code>min-content</code>, <code>fit-content</code> keywords.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-flexbox-1/#min-size-auto">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'min-width' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds the <code>auto</code> keyword and uses it as the initial value.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/visudet.html#min-max-widths">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'min-width' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`min-width`

1

12

1

CSS 2.1 leaves the behavior of `min-width` with [`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table) undefined. Firefox supports applying `min-width` to `table` elements.

7

4

CSS 2.1 leaves the behavior of `min-width` with [`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table) undefined. Opera supports applying `min-width` to `table` elements.

1

4.4

18

4

CSS 2.1 leaves the behavior of `min-width` with [`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table) undefined. Firefox supports applying `min-width` to `table` elements.

10.1

1

1.0

`auto`

21

Chrome uses `auto` as the initial value for `min-width`.

12

Edge uses `auto` as the initial value for `min-width`.

34

16-22

Firefox 18 and later (until the value was removed), used `auto` as the initial value for `min-width`.

No

12.1

Opera uses `auto` as the initial value for `min-width`.

No

37

Chrome uses `auto` as the initial value for `min-width`.

25

Chrome uses `auto` as the initial value for `min-width`.

34

16-22

Firefox 18 and later (until the value was removed), used `auto` as the initial value for `min-width`.

14

Opera uses `auto` as the initial value for `min-width`.

No

1.5

Samsung Internet uses `auto` as the initial value for `min-width`.

`fit-content`

46

25

79

79

3

Firefox implements the definitions given in CSS3 Basic Box. This defines `available` and not `fit-available`. Also, the definition of `fit-content` is simpler than in CSS3 Sizing.

No

33

15

11

6.1

46

≤37

46

4

Firefox implements the definitions given in CSS3 Basic Box. This defines `available` and not `fit-available`. Also, the definition of `fit-content` is simpler than in CSS3 Sizing.

33

11

7

5.0

`max-content`

46

25

79

79

66

3

No

33

15

11

2

46

≤37

46

66

4

33

11

1

5.0

`min-content`

46

25

25-48

79

79

66

3

No

33

≤15

≤15-35

11

2

46

≤37

≤37-48

46

25

25-48

66

4

33

≤14

≤14-35

11

1

5.0

1.5

1.5-5.0

`stretch`

22

79

No

No

15

No

4.4

25

No

14

No

1.5

## See also

- [`width`](width), [`max-width`](max-width)
- The [box model](css_box_model/introduction_to_the_css_box_model), [`box-sizing`](box-sizing)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/min-width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/min-width</a>
