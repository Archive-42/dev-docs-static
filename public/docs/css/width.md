# width

The `width` CSS property sets an element's width. By default, it sets the width of the [content area](css_box_model/introduction_to_the_css_box_model#content-area), but if [`box-sizing`](box-sizing) is set to `border-box`, it sets the width of the [border area](css_box_model/introduction_to_the_css_box_model#border-area).

The [`min-width`](min-width) and [`max-width`](max-width) properties override `width`.

## Syntax

    /* <length> values */
    width: 300px;
    width: 25em;

    /* <percentage> value */
    width: 75%;

    /* Keyword values */
    width: max-content;
    width: min-content;
    width: fit-content(20em);
    width: auto;

    /* Global values */
    width: inherit;
    width: initial;
    width: unset;

### Values

[`<length>`](length)  
Defines the width as an absolute value.

[`<percentage>`](percentage)  
Defines the width as a percentage of the containing block's width.

`auto`  
The browser will calculate and select a width for the specified element.

`max-content`  
The intrinsic preferred width.

`min-content`  
The intrinsic minimum width.

`fit-content(<length-percentage>`)  
Uses the fit-content formula with the available space replaced by the specified argument, i.e. `min(max-content, max(min-content, <length-percentage>))`.

## Accessibility concerns

Ensure that elements set with a `width` aren't truncated and/or don't obscure other content when the page is zoomed to increase text size.

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements but non-replaced inline elements, table rows, and row groups</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>a percentage or <code>auto</code> or the absolute length</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    auto | <length> | <percentage> | min-content | max-content | fit-content | fit-content(<length-percentage>)where
    <length-percentage> = <length> | <percentage>

## Examples

### Default width

    p.goldie {
      background: gold;
    }

    <p class="goldie">The Mozilla community produces a lot of great software.</p>

### Pixels and ems

    .px_length {
      width: 200px;
      background-color: red;
      color: white;
      border: 1px solid black;
    }

    .em_length {
      width: 20em;
      background-color: white;
      color: red;
      border: 1px solid black;
    }

    <div class="px_length">Width measured in px</div>
    <div class="em_length">Width measured in em</div>

### Percentage

    .percent {
      width: 20%;
      background-color: silver;
      border: 1px solid red;
    }

    <div class="percent">Width in percentage</div>

### max-content

    p.maxgreen {
      background: lightgreen;
      width: intrinsic;           /* Safari/WebKit uses a non-standard name */
      width: -moz-max-content;    /* Firefox/Gecko */
      width: -webkit-max-content; /* Chrome */
      width: max-content;
    }

    <p class="maxgreen">The Mozilla community produces a lot of great software.</p>

### min-content

    p.minblue {
      background: lightblue;
      width: -moz-min-content;    /* Firefox */
      width: -webkit-min-content; /* Chrome */
      width: min-content;
    }

    <p class="minblue">The Mozilla community produces a lot of great software.</p>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-sizing-4/#width-height-keywords">CSS Box Sizing Module Level 4<br />
<span class="small">The definition of 'width' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-sizing-3/#width-height-keywords">CSS Box Sizing Module Level 3<br />
<span class="small">The definition of 'width' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the <code>max-content</code>, <code>min-content</code>, <code>fit-content</code> keywords.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/visudet.html#the-width-property">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'width' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Precises on which element it applies to.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#width">CSS Level 1<br />
<span class="small">The definition of 'width' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`width`

1

12

1

4

3.5

1

1

18

4

10.1

1

1.0

`animatable`

26

12

16

11

15

6.1

4.4

26

16

14

6.1

1.5

`fill`

46

79

No

No

33

12

46

46

No

33

12

5.0

`fit-content`

46

22

1-48

79

79

3

No

33

15

15-35

11

6.1

2

46

≤37

1-48

46

25

18-48

4

33

14

14-35

11

7

1

5.0

1.5

1.0-5.0

`fit-content_function`

No

No

No

See [bug 1312588](https://bugzil.la/1312588).

No

No

No

No

No

No

No

No

No

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

2

46

46

66

4

43

11

1

5.0

`min-content`

46

1-48

79

66

3

No

33

15-35

11

2

46

1-48

46

18-48

66

4

33

14-35

11

1

5.0

1.0-5.0

`stretch`

22

79

3

No

15

6.1

4.4

25

4

14

6.1

5.0

## See also

- [The box model](css_box_model/introduction_to_the_css_box_model)
- [`height`](height)
- [`box-sizing`](box-sizing)
- [`min-width`](min-width), [`max-width`](max-width)
- The mapped logical properties: [`block-size`](block-size), [`inline-size`](inline-size)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/width</a>
