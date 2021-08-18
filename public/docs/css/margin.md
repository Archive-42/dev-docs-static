# margin

The `margin` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the [margin area](css_box_model/introduction_to_the_css_box_model) on all four sides of an element. It is a [shorthand](shorthand_properties) for [`margin-top`](margin-top), [`margin-right`](margin-right), [`margin-bottom`](margin-bottom), and [`margin-left`](margin-left).

The top and bottom margins have no effect on _non-[replaced](replaced_element)_ inline elements, such as [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) or [`<code>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/code).

**Note:** Margins create extra space around an element. In contrast, [`padding`](padding) creates extra space _within_ an element.

## Syntax

    /* Apply to all four sides */
    margin: 1em;
    margin: -3px;

    /* vertical | horizontal */
    margin: 5% auto;

    /* top | horizontal | bottom */
    margin: 1em auto 2em;

    /* top | right | bottom | left */
    margin: 2px 1em 0 auto;

    /* Global values */
    margin: inherit;
    margin: initial;
    margin: unset;

The `margin` property may be specified using one, two, three, or four values. Each value is a [`<length>`](length), a [`<percentage>`](percentage), or the keyword `auto`. Negative values draw the element closer to its neighbors than it would be by default.

- When **one** value is specified, it applies the same margin to **all four sides**.
- When **two** values are specified, the first margin applies to the **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first margin applies to the **top**, the second to the **right and left**, the third to the **bottom**.
- When **four** values are specified, the margins apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

### Values

**[`<length>`](length)**  
The size of the margin as a fixed value.

[`<percentage>`](percentage)  
The size of the margin as a percentage, relative to the _width_ of the [containing block](containing_block).

`auto`  
The browser selects a suitable margin to use. For example, in certain cases this value can be used to center an element.

### Formal syntax

    [ <length> | <percentage> | auto ]{1,4}

## Examples

### Simple example

#### HTML

    <div class="center">This element is centered.</div>

    <div class="outside">This element is positioned outside of its container.</div>

#### CSS

    .center {
      margin: auto;
      background: lime;
      width: 66%;
    }

    .outside {
      margin: 3rem 0 0 -3rem;
      background: cyan;
      width: 66%;
    }

### More examples

    margin: 5%;                 /* All sides: 5% margin */

    margin: 10px;               /* All sides: 10px margin */

    margin: 1.6em 20px;         /* top and bottom: 1.6em margin */
                                /* left and right: 20px margin  */

    margin: 10px 3% -1em;       /* top:            10px margin */
                                /* left and right: 3% margin   */
                                /* bottom:         -1em margin */

    margin: 10px 3px 30px 5px;  /* top:    10px margin */
                                /* right:  3px margin  */
                                /* bottom: 30px margin */
                                /* left:   5px margin  */

    margin: 2em auto;           /* top and bottom: 2em margin   */
                                /* Box is horizontally centered */

    margin: auto;               /* top and bottom: 0 margin     */
                                /* Box is horizontally centered */

## Notes

### Horizontal centering

To center something horizontally in modern browsers, you can use [`display`](display)`: flex; `[`justify-content`](justify-content)`: center;` .

However, in older browsers like IE8-9 that do not support Flexible Box Layout, these are not available. In order to center an element inside its parent, use `margin: 0 auto;`.

### Margin collapsing

Elements' top and bottom margins are sometimes collapsed into a single margin that is equal to the larger of the two margins. See [Mastering margin collapsing](css_box_model/mastering_margin_collapsing) for more information.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-box-3/#margin">CSS Basic Box Model<br />
<span class="small">The definition of 'margin' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No significant change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#margin-properties">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'margin' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Removes the effect of top and bottom margins on inline elements.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#margin">CSS Level 1<br />
<span class="small">The definition of 'margin' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="margin-bottom"><code>margin-bottom</code></a>: <code>0</code></li><li><a href="margin-left"><code>margin-left</code></a>: <code>0</code></li><li><a href="margin-right"><code>margin-right</code></a>: <code>0</code></li><li><a href="margin-top"><code>margin-top</code></a>: <code>0</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements, except elements with table <a href="display"><code>display</code></a> types other than <code>table-caption</code>, <code>table</code> and <code>inline-table</code>. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="margin-bottom"><code>margin-bottom</code></a>: the percentage as specified or the absolute length</li><li><a href="margin-left"><code>margin-left</code></a>: the percentage as specified or the absolute length</li><li><a href="margin-right"><code>margin-right</code></a>: the percentage as specified or the absolute length</li><li><a href="margin-top"><code>margin-top</code></a>: the percentage as specified or the absolute length</li></ul></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

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

`margin`

1

12

1

3

3.5

1

1

18

4

10.1

1

1.0

`auto`

1

12

The `auto` value is not supported in quirks mode.

1

6

The `auto` value is not supported in quirks mode.

3.5

1

37

18

4

14

1

1.0

## See also

- <a href="css_box_model/introduction_to_the_css_box_model" class="internal">Introduction to the CSS basic box model</a>
- <a href="css_box_model/mastering_margin_collapsing" class="internal">Margin collapsing</a>
- [`margin-top`](margin-top), [`margin-right`](margin-right), [`margin-bottom`](margin-bottom), and [`margin-left`](margin-left)
- The mapped logical properties: [`margin-block-start`](margin-block-start), [`margin-block-end`](margin-block-end), [`margin-inline-start`](margin-inline-start), and [`margin-inline-end`](margin-inline-end) and the shorthands [`margin-block`](margin-block) and [`margin-inline`](margin-inline)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/margin</a>
