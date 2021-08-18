# max-height

The `max-height` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the maximum height of an element. It prevents the [used value](used_value) of the [`height`](height) property from becoming larger than the value specified for `max-height`.

`max-height` overrides [`height`](height), but [`min-height`](min-height) overrides `max-height`.

## Syntax

    /* <length> value */
    max-height: 3.5em;

    /* <percentage> value */
    max-height: 75%;

    /* Keyword values */
    max-height: none;
    max-height: max-content;
    max-height: min-content;
    max-height: fit-content(20em);

    /* Global values */
    max-height: inherit;
    max-height: initial;
    max-height: unset;

### Values

[`<length>`](length)  
Defines the `max-height` as an absolute value.

[`<percentage>`](percentage)  
Defines the `max-height` as a percentage of the containing block's height.

`none`  
No limit on the size of the box.

`max-content`  
The intrinsic preferred `max-height`.

`min-content`  
The intrinsic minimum `max-height`.

`fit-content(<length-percentage>`)  
Uses the `fit-content` formula with the available space replaced by the specified argument, i.e. `min(max-content, max(min-content, argument))`.

## Accessibility concerns

Ensure that elements set with a `max-height` are not truncated and/or do not obscure other content when the page is zoomed to increase text size.

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements but non-replaced inline elements, table columns, and column groups</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>The percentage is calculated with respect to the height of the generated box's containing block. If the height of the containing block is not specified explicitly (i.e., it depends on content height), and this element is not absolutely positioned, the percentage value is treated as <code>none</code>.</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>the percentage as specified or the absolute length or <code>none</code></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    none | <length-percentage> | min-content | max-content | fit-content | fit-content(<length-percentage>)where
    <length-percentage> = <length> | <percentage>

## Examples

### Setting max-height using percentage and keyword values

    table { max-height: 75%; }

    form { max-height: none; }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-sizing-4/#width-height-keywords">CSS Box Sizing Module Level 4<br />
<span class="small">The definition of 'max-height' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-sizing-3/#width-height-keywords">CSS Box Sizing Module Level 3<br />
<span class="small">The definition of 'max-height' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the <code>max-content</code>, <code>min-content</code>, <code>fit-content</code> keywords.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/visudet.html#min-max-heights">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'max-height' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`max-height`

18

12

1

CSS 2.1 leaves the behavior of `max-height` with [`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table) undefined. Firefox supports applying `max-height` to `table` elements.

7

7

CSS 2.1 leaves the behavior of `max-height` with [`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table) undefined. Opera supports applying `max-height` to `table` elements.

1.3

≤37

18

4

14

1

1.0

`fit-content`

46

25

79

79

3

Firefox implements the definitions given in CSS3 Basic Box. This defines `available` and not `fit-available`. Also, the definition of `fit-content` is simpler than in CSS3 Sizing.

No

44

11

6.1

2

46

≤37

46

25

4

Firefox implements the definitions given in CSS3 Basic Box. This defines `available` and not `fit-available`. Also, the definition of `fit-content` is simpler than in CSS3 Sizing.

43

11

7

1

5.0

1.5

`max-content`

46

79

66

3

No

44

11

9

46

46

66

4

43

11

9

5.0

`min-content`

46

79

66

3

No

44

11

9

46

46

66

4

43

11

9

5.0

`stretch`

28

79

No

No

15

No

4.4

28

No

15

No

1.5

## See also

- [The box model](css_box_model/introduction_to_the_css_box_model), [`box-sizing`](box-sizing)
- [`height`](height), [`min-height`](min-height)
- The mapped logical properties: [`max-inline-size`](max-inline-size), [`max-block-size`](max-block-size)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/max-height" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/max-height</a>
