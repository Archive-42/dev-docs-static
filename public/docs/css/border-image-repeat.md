# border-image-repeat

The `border-image-repeat` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines how the [edge regions](border-image-slice#edge-regions) of a source image are adjusted to fit the dimensions of an element's [border image](border-image).

## Syntax

    /* Keyword value */
    border-image-repeat: stretch;
    border-image-repeat: repeat;
    border-image-repeat: round;
    border-image-repeat: space;

    /* vertical | horizontal */
    border-image-repeat: round stretch;

    /* Global values */
    border-image-repeat: inherit;
    border-image-repeat: initial;
    border-image-repeat: unset;

The `border-image-repeat` property may be specified using one or two values chosen from the list of values below.

- When **one** value is specified, it applies the same behavior on **all four sides**.
- When **two** values are specified, the first applies to the **top and bottom**, the second to the **left and right**.

### Values

`stretch`  
The source image's edge regions are stretched to fill the gap between each border.

`repeat`  
The source image's edge regions are tiled (repeated) to fill the gap between each border. Tiles may be clipped to achieve the proper fit.

`round`  
The source image's edge regions are tiled (repeated) to fill the gap between each border. Tiles may be stretched to achieve the proper fit.

`space`  
The source image's edge regions are tiled (repeated) to fill the gap between each border. Extra space will be distributed in between tiles to achieve the proper fit.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>stretch</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, except internal table elements when <a href="border-collapse"><code>border-collapse</code></a> is <code>collapse</code>. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ stretch | repeat | round | space ]{1,2}

## Examples

### Repeating border images

#### CSS

    #bordered {
      width: 12rem;
      margin-bottom: 1rem;
      padding: 1rem;
      border: 40px solid;
      border-image: url("https://mdn.mozillademos.org/files/4127/border.png") 27;
      border-image-repeat: stretch;  /* Can be changed in the live sample */
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-border-image-repeat">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-image-repeat' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-image-repeat`

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

9.3

1.0

`round`

30

12

15

11

17

9.1

≤37

30

15

18

9.3

2.0

`space`

56

12

50

11

43

9.1

56

56

50

43

9.3

6.0

## See also

- [Backgrounds and borders](css_backgrounds_and_borders)
- [Learn CSS: Backgrounds and borders](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Backgrounds_and_borders)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-repeat" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-repeat</a>
