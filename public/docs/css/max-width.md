# max-width

The `max-width` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the maximum width of an element. It prevents the [used value](used_value) of the [`width`](width) property from becoming larger than the value specified by `max-width`.

`max-width` overrides [`width`](width), but [`min-width`](min-width) overrides `max-width`.

## Syntax

    /* <length> value */
    max-width: 3.5em;

    /* <percentage> value */
    max-width: 75%;

    /* Keyword values */
    max-width: none;
    max-width: max-content;
    max-width: min-content;
    max-width: fit-content(20em);

    /* Global values */
    max-width: inherit;
    max-width: initial;
    max-width: unset;

### Values

[`<length>`](length)  
Defines the `max-width` as an absolute value.

[`<percentage>`](percentage)  
Defines the `max-width` as a percentage of the containing block's width.

`none`  
No limit on the size of the box.

`max-content`  
The intrinsic preferred `max-width`.

`min-content`  
The intrinsic minimum `max-width`.

`fit-content(<length-percentage>`)  
Uses the `fit-content` formula with the available space replaced by the specified argument, i.e. `min(max-content, max(min-content, argument))`.

## Accessibility concerns

Ensure that elements set with a `max-width` are not truncated and/or do not obscure other content when the page is zoomed to increase text size.

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements but non-replaced inline elements, table rows, and row groups</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>the percentage as specified or the absolute length or <code>none</code></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    none | <length-percentage> | min-content | max-content | fit-content | fit-content(<length-percentage>)where
    <length-percentage> = <length> | <percentage>

## Examples

### Setting max width in pixels

In this example, the "child" will be either 150 pixels wide or the width of the "parent," whichever is smaller.

#### HTML

    <div id="parent">
      <div id="child">
        Fusce pulvinar vestibulum eros, sed luctus ex lobortis quis.
      </div>
    </div>

#### CSS

    #parent {
      background: lightblue;
      width: 300px;
    }

    #child {
      background: gold;
      width: 100%;
      max-width: 150px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-sizing-4/#width-height-keywords">CSS Box Sizing Module Level 4<br />
<span class="small">The definition of 'max-width' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-sizing-3/#width-height-keywords">CSS Box Sizing Module Level 3<br />
<span class="small">The definition of 'max-width' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the <code>max-content</code>, <code>min-content</code>, <code>fit-content</code> keywords.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/visudet.html#min-max-widths">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'max-width' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`max-width`

1

12

1

CSS 2.1 leaves the behavior of `max-width` with [`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table) undefined. Firefox supports applying `max-width` to `table` elements.

7

4

CSS 2.1 leaves the behavior of `max-width` with [`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table) undefined. Opera supports applying `max-width` to `table` elements.

1

4.4

18

4

CSS 2.1 leaves the behavior of `max-width` with [`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table) undefined. Firefox supports applying `max-width` to `table` elements.

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

4

Firefox implements the definitions given in CSS3 Basic Box. This defines `available` and not `fit-available`. Also, the definition of `fit-content` is simpler than in CSS3 Sizing.

43

11

7

1

5.0

`max-content`

46

22

79

79

66

3

No

44

11

6.1

2

46

≤37

46

66

4

43

11

7

1

5.0

`min-content`

46

25

79

79

66

3

No

44

11

6.1

2

46

46

66

4

43

11

7

1

5.0

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

- [The box model](css_box_model/introduction_to_the_css_box_model), [`box-sizing`](box-sizing)
- [`width`](width), [`min-width`](min-width)
- The mapped logical properties: [`max-inline-size`](max-inline-size), [`max-block-size`](max-block-size)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/max-width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/max-width</a>
