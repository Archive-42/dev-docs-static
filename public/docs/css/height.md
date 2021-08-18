# height

The `height` CSS property specifies the height of an element. By default, the property defines the height of the [content area](css_box_model/introduction_to_the_css_box_model#content-area). If [`box-sizing`](box-sizing) is set to `border-box`, however, it instead determines the height of the [border area](css_box_model/introduction_to_the_css_box_model#border-area).

The [`min-height`](min-height) and [`max-height`](max-height) properties override `height`.

## Syntax

    /* <length> values */
    height: 120px;
    height: 10em;

    /* <percentage> value */
    height: 75%;

    /* Keyword values */
    height: max-content;
    height: min-content;
    height: fit-content(20em);
    height: auto;

    /* Global values */
    height: inherit;
    height: initial;
    height: unset;

### Values

[`<length>`](length)  
Defines the height as an absolute value.

[`<percentage>`](percentage)  
Defines the height as a percentage of the containing block's height.

`auto`  
The browser will calculate and select a height for the specified element.

`max-content`  
The intrinsic preferred height.

`min-content`  
The intrinsic minimum height.

`fit-content(<length-percentage>`)  
Uses the fit-content formula with the available space replaced by the specified argument, i.e. `min(max-content, max(min-content, <length-percentage>))`.

## Accessibility concerns

Ensure that elements set with a `height` aren't truncated and/or don't obscure other content when the page is zoomed to increase text size.

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements but non-replaced inline elements, table columns, and column groups</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>The percentage is calculated with respect to the height of the generated box's containing block. If the height of the containing block is not specified explicitly (i.e., it depends on content height), and this element is not absolutely positioned, the value computes to <code>auto</code>. A percentage height on the root element is relative to the initial containing block.</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>a percentage or <code>auto</code> or the absolute length</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    auto | <length> | <percentage> | min-content | max-content | fit-content | fit-content(<length-percentage>)where
    <length-percentage> = <length> | <percentage>

## Examples

### Setting height using pixels and percentages

#### HTML

    <div id="taller">I'm 50 pixels tall.</div>
    <div id="shorter">I'm 25 pixels tall.</div>
    <div id="parent">
      <div id="child">
        I'm half the height of my parent.
      </div>
    </div>

#### CSS

    div {
      width: 250px;
      margin-bottom: 5px;
      border: 2px solid blue;
    }

    #taller {
      height: 50px;
    }

    #shorter {
      height: 25px;
    }

    #parent {
      height: 100px;
    }

    #child {
      height: 50%;
      width: 75%;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-sizing-4/#width-height-keywords">CSS Box Sizing Module Level 4<br />
<span class="small">The definition of 'height' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-sizing-3/#width-height-keywords">CSS Box Sizing Module Level 3<br />
<span class="small">The definition of 'height' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the <code>max-content</code>, <code>min-content</code>, <code>fit-content</code> keywords.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/visudet.html#the-height-property">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'height' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds support for the <a href="length"><code>&lt;length&gt;</code></a> values and precises on which element it applies to.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#height">CSS Level 1<br />
<span class="small">The definition of 'height' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`height`

1

12

1

4

7

1

1

18

4

10.1

1

1.0

`fit-content`

46

79

No

No

33

11

9

46

46

No

33

11

9

5.0

`max-content`

46

79

66

3

No

44

11

46

46

66

4

43

11

5.0

`min-content`

46

79

66

3

No

44

11

46

46

66

4

43

11

5.0

`stretch`

28

79

No

No

15

9

4.4

28

No

15

9

5.0

## See also

- [The box model](css_box_model/introduction_to_the_css_box_model)
- [`width`](width)
- [`box-sizing`](box-sizing)
- [`min-height`](min-height), [`max-height`](max-height)
- The mapped logical properties: [`block-size`](block-size), [`inline-size`](inline-size)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/height" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/height</a>
