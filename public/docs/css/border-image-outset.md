# border-image-outset

The `border-image-outset` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the distance by which an element's [border image](border-image) is set out from its border box.

The parts of the border image that are rendered outside the element's border box with `border-image-outset` do not trigger overflow scrollbars and don't capture mouse events.

## Syntax

    /* <length> value */
    border-image-outset: 1rem;

    /* <number> value */
    border-image-outset: 1.5;

    /* vertical | horizontal */
    border-image-outset: 1 1.2;

    /* top | horizontal | bottom */
    border-image-outset: 30px 2 45px;

    /* top | right | bottom | left */
    border-image-outset: 7px 12px 14px 5px;

    /* Global values */
    border-image-outset: inherit;
    border-image-outset: initial;
    border-image-outset: unset;

The `border-image-outset` property may be specified as one, two, three, or four values. Each value is a [`<length>`](length) or [`<number>`](number). Negative values are invalid and will cause the `border-image-outset` declaration to be ignored.

1.  If **one** value is specified, it applies to **all four sides**.
2.  If **two** values are specified, the first applies to the **top and bottom** and the second to the **left and right**.
3.  If **three** values are specified, the first applies to the **top**, the second to the **left and right**, and the third to the **bottom**.
4.  If **four** values are specified, they apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

### Values

[`<length>`](length)  
The size of the `border-image` outset as a dimension — a number with a unit.

[`<number>`](number)  
The size of the `border-image` outset as a multiple of the element's corresponding [`border-width`](border-width)s. For example, if an element has `border-width: 1em 2px 0 1.5rem`, and `border-image-outset: 2`, the final `border-image-outset` would be calculated as `2em 4px 0 3rem`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, except internal table elements when <a href="border-collapse"><code>border-collapse</code></a> is <code>collapse</code>. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr><tr class="odd"><td>Animation type</td><td>by computed value type</td></tr></tbody></table>

## Formal syntax

    [ <length> | <number> ]{1,4}

## Examples

### Outsetting a border image

#### HTML

    <div id="outset">This element has an outset border image!</div>

#### CSS

    #outset {
      width: 10rem;
      background: #cef;
      border: 1.4rem solid;
      border-image: radial-gradient(#ff2, #55f) 40;
      border-image-outset: 1.5;  /* 1.5 × 1.4rem = 2.1rem */
      margin: 2.1rem;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-border-image-outset">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-image-outset' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-image-outset`

15

12

15

11

15

6

≤37

18

15

14

6

1.0

## See also

- [Backgrounds and borders](css_backgrounds_and_borders)
- [Learn CSS: Backgrounds and borders](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Backgrounds_and_borders)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-outset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-outset</a>
