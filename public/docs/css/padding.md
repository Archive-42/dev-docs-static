# padding

The `padding` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](shorthand_properties) sets the [padding area](css_box_model/introduction_to_the_css_box_model#padding-area) on all four sides of an element at once.

An element's padding area is the space between its content and its border.

**Note:** Padding creates extra space within an element. In contrast, [`margin`](margin) creates extra space _around_ an element.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`padding-bottom`](padding-bottom)
- [`padding-left`](padding-left)
- [`padding-right`](padding-right)
- [`padding-top`](padding-top)

## Syntax

    /* Apply to all four sides */
    padding: 1em;

    /* vertical | horizontal */
    padding: 5% 10%;

    /* top | horizontal | bottom */
    padding: 1em 2em 2em;

    /* top | right | bottom | left */
    padding: 5px 1em 0 2em;

    /* Global values */
    padding: inherit;
    padding: initial;
    padding: unset;

The `padding` property may be specified using one, two, three, or four values. Each value is a [`<length>`](length) or a [`<percentage>`](percentage). Negative values are invalid.

- When **one** value is specified, it applies the same padding to **all four sides**.
- When **two** values are specified, the first padding applies to the **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first padding applies to the **top**, the second to the **right and left**, the third to the **bottom**.
- When **four** values are specified, the paddings apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

### Values

[`<length>`](length)  
The size of the padding as a fixed value.

[`<percentage>`](percentage)  
The size of the padding as a percentage, relative to the _width_ of the containing block.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="padding-bottom"><code>padding-bottom</code></a>: <code>0</code></li><li><a href="padding-left"><code>padding-left</code></a>: <code>0</code></li><li><a href="padding-right"><code>padding-right</code></a>: <code>0</code></li><li><a href="padding-top"><code>padding-top</code></a>: <code>0</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements, except <code>table-row-group</code>, <code>table-header-group</code>, <code>table-footer-group</code>, <code>table-row</code>, <code>table-column-group</code> and <code>table-column</code>. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="padding-bottom"><code>padding-bottom</code></a>: the percentage as specified or the absolute length</li><li><a href="padding-left"><code>padding-left</code></a>: the percentage as specified or the absolute length</li><li><a href="padding-right"><code>padding-right</code></a>: the percentage as specified or the absolute length</li><li><a href="padding-top"><code>padding-top</code></a>: the percentage as specified or the absolute length</li></ul></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    [ <length> | <percentage> ]{1,4}

## Examples

### Setting padding with pixels

#### HTML

    <h4>This element has moderate padding.</h4>
    <h3>The padding is huge in this element!</h3>

#### CSS

    h4 {
      background-color: lime;
      padding: 20px 50px;
    }

    h3 {
      background-color: cyan;
      padding: 110px 50px 50px 110px;
    }

#### Result

### Setting padding with pixels and percentages

    padding: 5%;                /* All sides: 5% padding */

    padding: 10px;              /* All sides: 10px padding */

    padding: 10px 20px;         /* top and bottom: 10px padding */
                                /* left and right: 20px padding */

    padding: 10px 3% 20px;      /* top:            10px padding */
                                /* left and right: 3% padding   */
                                /* bottom:         20px padding */

    padding: 1em 3px 30px 5px;  /* top:    1em padding  */
                                /* right:  3px padding  */
                                /* bottom: 30px padding */
                                /* left:   5px padding  */

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-box-3/#padding-shorthand">CSS Basic Box Model<br />
<span class="small">The definition of 'padding' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#propdef-padding">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'padding' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#padding">CSS Level 1<br />
<span class="small">The definition of 'padding' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`padding`

1

12

1

4

3.5

1

≤37

18

4

14

1

1.0

## See also

- [Introduction to the CSS basic box model](css_box_model/introduction_to_the_css_box_model)
- [`padding-top`](padding-top), [`padding-right`](padding-right), [`padding-bottom`](padding-bottom), and [`padding-left`](padding-left).
- The mapped logical properties: [`padding-block-start`](padding-block-start), [`padding-block-end`](padding-block-end), [`padding-inline-start`](padding-inline-start), and [`padding-inline-end`](padding-inline-end) and the shorthands [`padding-block`](padding-block) and [`padding-inline`](padding-inline)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/padding" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/padding</a>
