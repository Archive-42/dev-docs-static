# line-height

The `line-height` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the height of a line box. It's commonly used to set the distance between lines of text. On block-level elements, it specifies the minimum height of line boxes within the element. On non-[replaced](replaced_element) inline elements, it specifies the height that is used to calculate line box height.

## Syntax

    /* Keyword value */
    line-height: normal;

    /* Unitless values: use this number multiplied
    by the element's font size */
    line-height: 3.5;

    /* <length> values */
    line-height: 3em;

    /* <percentage> values */
    line-height: 34%;

    /* Global values */
    line-height: inherit;
    line-height: initial;
    line-height: unset;

The `line-height` property is specified as any one of the following:

- a `<number>`
- a `<length>`
- a `<percentage>`
- the keyword `normal`.

### Values

`normal`  
Depends on the user agent. Desktop browsers (including Firefox) use a default value of roughly `1.2`, depending on the element's `font-family`.

`<number>` (unitless)  
The used value is this unitless [`<number>`](number) multiplied by the element's own font size. The computed value is the same as the specified `<number>`. In most cases, **this is the preferred way** to set `line-height` and avoid unexpected results due to inheritance.

`<length>`  
The specified [`<length>`](length) is used in the calculation of the line box height. Values given in **em** units may produce unexpected results (see example below).

`<percentage>`  
Relative to the font size of the element itself. The computed value is this [`<percentage>`](percentage) multiplied by the element's computed font size. **Percentage** values may produce unexpected results (see the second example below).

`-moz-block-height` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Sets the line height to the content height of the current block.

## Accessibility concerns

Use a minimum value of `1.5` for `line-height` for main paragraph content. This will help people experiencing low vision conditions, as well as people with cognitive concerns such as Dyslexia. If the page is zoomed to increase the text size, using a unitless value ensures that the line height will scale proportionately.

[W3C Understanding WCAG 2.1](https://www.w3.org/TR/WCAG21/#visual-presentation)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td>Percentages</td><td>refer to the font size of the element itself</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>for percentage and length values, the absolute length, otherwise as specified</td></tr><tr class="even"><td>Animation type</td><td>either number or length</td></tr></tbody></table>

## Formal syntax

    normal | <number> | <length> | <percentage>

## Examples

### Basic example

    /* All rules below have the same resultant line height */

    div { line-height: 1.2;   font-size: 10pt; }   /* number/unitless */
    div { line-height: 1.2em; font-size: 10pt; }   /* length */
    div { line-height: 120%;  font-size: 10pt; }   /* percentage */
    div { font: 10pt/1.2  Georgia,"Bitstream Charter",serif; } /* font shorthand */

It is often more convenient to set `line-height` by using the [`font`](font) shorthand as shown above, but this requires the `font-family` property to be specified as well.

### Prefer unitless numbers for line-height values

This example shows why it is better to use [`<number>`](number) values instead of [`<length>`](length) values. We will use two [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) elements. The first, with the green border, uses a unitless `line-height` value. The second, with the red border, uses a `line-height` value defined in `em`s.

#### HTML

    <div class="box green">
     <h1>Avoid unexpected results by using unitless line-height.</h1>
      length and percentage line-heights have poor inheritance behavior ...
    </div>

    <div class="box red">
     <h1>Avoid unexpected results by using unitless line-height.</h1>
      length and percentage line-heights have poor inheritance behavior ...
    </div>

    <!-- The first <h1> line-height is calculated from its own font-size   (30px × 1.1) = 33px  -->
    <!-- The second <h1> line-height results from the red div's font-size  (15px × 1.1) = 16.5px,  probably not what you want -->

#### CSS

    .green {
      line-height: 1.1;
      border: solid limegreen;
    }

    .red {
      line-height: 1.1em;
      border: solid red;
    }

    h1 {
      font-size: 30px;
    }

    .box {
      width: 18em;
      display: inline-block;
      vertical-align: top;
      font-size: 15px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/visudet.html#propdef-line-height">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'line-height' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#line-height">CSS Level 1<br />
<span class="small">The definition of 'line-height' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`line-height`

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

`-moz-block-height`

No

No

3.6

No

No

No

No

No

4

No

No

No

## See also

- [`font`](font), [`font-size`](font-size)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/line-height" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/line-height</a>
