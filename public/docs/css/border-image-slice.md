# border-image-slice

The `border-image-slice` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property divides the image specified by [`border-image-source`](border-image-source) into regions. These regions form the components of an element's [border image](border-image).

The slicing process creates nine regions in total: four corners, four edges, and a middle region. Four slice lines, set a given distance from their respective sides, control the size of the regions.

[<img src="data:image/png;base64,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" alt="The nine regions defined by the border-image or border-image-slice properties" width="657" height="347" />](border-image-slice/border-image-slice.png)

The above diagram illustrates the location of each region.

- Zones 1-4 are <span id="corner-regions">corner regions</span>. Each one is used a single time to form the corners of the final border image.
- Zones 5-8 are <span id="edge-regions">edge regions</span>. These are [repeated, scaled, or otherwise modified](border-image-repeat) in the final border image to match the dimensions of the element.
- Zone 9 is the <span id="middle-region">middle region</span>. It is discarded by default, but is used like a background image if the keyword `fill` is set.

The [`border-image-repeat`](border-image-repeat), [`border-image-width`](border-image-width), and [`border-image-outset`](border-image-outset) properties determine how these regions are used to form the final border image.

## Syntax

    /* All sides */
    border-image-slice: 30%;

    /* vertical | horizontal */
    border-image-slice: 10% 30%;

    /* top | horizontal | bottom */
    border-image-slice: 30 30% 45;

    /* top | right | bottom | left */
    border-image-slice: 7 12 14 5;

    /* Using the `fill` keyword */
    border-image-slice: 10% fill 7 12;

    /* Global values */
    border-image-slice: inherit;
    border-image-slice: initial;
    border-image-slice: unset;

The `border-image-slice` property may be specified using one to four `<number-percentage>` values to represent the position of each image slice. Negative values are invalid; values greater than their corresponding dimension are clamped to `100%`.

- When **one** position is specified, it creates all four slices at the same distance from their respective sides.
- When **two** positions are specified, the first value creates slices measured from the **top and bottom**, the second creates slices measured from the **left and right**.
- When **three** positions are specified, the first value creates a slice measured from the **top**, the second creates slices measured from the **left and right**, the third creates a slice measured from the **bottom**.
- When **four** positions are specified, they create slices measured from the **top**, **right**, **bottom**, and **left** in that order (clockwise).

The optional `fill` value, if used, can be placed anywhere in the declaration.

### Values

[`<number>`](number)  
Represents an edge offset in _pixels_ for raster images and _coordinates_ for vector images. For vector images, the number is relative to the element's size, not the size of the source image, so percentages are generally preferable in these cases.

[`<percentage>`](percentage)  
Represents an edge offset as a percentage of the source image's size: the width of the image for horizontal offsets, the height for vertical offsets.

`fill`  
Preserves the middle image region and displays it like a background image, but stacked above the actual [`background`](background). Its width and height are sized to match the top and left image regions, respectively.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>100%</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, except internal table elements when <a href="border-collapse"><code>border-collapse</code></a> is <code>collapse</code>. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the size of the border image</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>one to four percentage(s) (as specified) or absolute length(s), plus the keyword <code>fill</code> if specified</td></tr><tr class="even"><td>Animation type</td><td>by computed value type</td></tr></tbody></table>

## Formal syntax

    <number-percentage>{1,4} && fill?where
    <number-percentage> = <number> | <percentage>

## Examples

### Adjustable border width and slice

The following example shows a simple `<div>` with a border image set on it. The source image for the borders is as follows:

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAABaBAMAAADKhlwxAAAAFVBMVEX////2nTzmZGXu7u72nTzmZGXu7u5STD5TAAAABHRSTlMAoKCgEjok+wAAAT5JREFUeF7tlkGqwjAURaNuwA8uQIQ/FwTnQlcgZAVC9r8EIVx66q0U7sBZOj29p03y3iNFz6V8PH+FZ0339byku+m4Qct/fS7xaXp8oYSr4lJPyKGEq+JST8ihhBWf1cihhHscNXIoYcVRI4cS7nHUyKGEFZcauVOFFZdacqcKE5dacqMKE5dacqMKE+9q5EYVnuNdjdxo9nb2J9Eqsx2MTic7+aiqsoqNuiHrtKiLswmRT598suVT0/Fti/qnD+3qdGNZ9/ZaU98y1A051I4DdUMO9aNGjRzqZYQaOdRLFDVyqJU/asmNWmtJjdyota3UyI3aSJBacqc2bqRGbtRGWVcjN1psTHY1cqPZ29mfRKvMdjA6nezko6rKKjbqhqzToi7OJkQ0fdLJlk/N391jxz123GPHPXbcY8c99g1A7me1IHQX+QAAAABJRU5ErkJggg==" alt="nice multi-colored diamonds" width="90" height="90" />

The diamonds are 30px across, therefore setting 30 pixels as the value for both `border-width` and `border-image-slice` will get you complete and fairly crisp diamonds in your border:

    border-width: 30px;
    border-image-slice: 30;

These are the default values we have used in this example. However, we have also provided two sliders to allow you to dynamically change the values of the above two properties, allowing you to appreciate the effect they have:

`border-image-slice` Changes the size of the image slice sampled for use in each border and border corner (and the content area, if the `fill` keyword is used) ??? varying this away from 30 causes the border to look somewhat irregular, but can have some interesting effects.

`border-width`: Changes the width of the border. The sampled image size is scaled to fit inside the border, which means that if the width is bigger than the slice, the image can start to look somewhat pixelated (unless of course you use an SVG image).

#### HTML

    <div class="wrapper">
      <div></div>
    </div>

    <ul>
      <li>
        <label for="width">slide to adjust <code>border-width</code></label>
        <input type="range" min="10" max="45" id="width">
        <output id="width-output">30px</output>
      </li>
      <li>
        <label for="slice">slide to adjust <code>border-image-slice</code></label>
        <input type="range" min="10" max="45" id="slice">
        <output id="slice-output">30</output>
      </li>
    </ul>

#### CSS

    .wrapper {
      width: 400px;
      height: 300px;
    }

    div > div {
      width: 300px;
      height: 200px;
      border-width: 30px;
      border-style: solid;
      border-image: url(https://interactive-examples.mdn.mozilla.net/media/examples/border-diamonds.png);
      border-image-slice: 30;
      border-image-repeat: round;
    }

    li {
      display: flex;
      place-content: center;
    }

#### JavaScript

    const widthSlider = document.getElementById('width');
    const sliceSlider = document.getElementById('slice');
    const widthOutput = document.getElementById('width-output');
    const sliceOutput = document.getElementById('slice-output');
    const divElem = document.querySelector('div > div');

    widthSlider.addEventListener('input', () => {
      const newValue = widthSlider.value + 'px';
      divElem.style.borderWidth = newValue;
      widthOutput.textContent = newValue;
    })

    sliceSlider.addEventListener('input', () => {
      const newValue = sliceSlider.value;
      divElem.style.borderImageSlice = newValue;
      sliceOutput.textContent = newValue;
    })

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-border-image-slice">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-image-slice' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-image-slice`

15

12

15

\["Small SVGs are incorrectly stretched, because percentages in [`border-image-slice`](https://developer.mozilla.org/docs/Web/CSS/border-image-slice) are computed to integers instead of floats ([bug 1284797](https://bugzil.la/1284797)).", "Until Firefox 47, SVGs without viewport were not sliced correctly ([bug 619500](https://bugzil.la/619500)).", "From Firefox 48 until Firefox 49, SVGs without viewport are displayed the same as SVGs with viewport, but if the slices are not exactly 50%, they are incorrectly stretched ([bug 1264809](https://bugzil.la/1264809)).", "Until Firefox 57, an issue persisted for SVGs without viewport when [e10s](https://wiki.mozilla.org/Electrolysis) was disabled ([bug 1290782](https://bugzil.la/1290782))."\]

11

15

6

???37

4.1

18

15

\["Small SVGs are incorrectly stretched, because percentages in [`border-image-slice`](https://developer.mozilla.org/docs/Web/CSS/border-image-slice) are computed to integers instead of floats ([bug 1284797](https://bugzil.la/1284797)).", "Until Firefox 47, SVGs without viewport were not sliced correctly ([bug 619500](https://bugzil.la/619500)).", "From Firefox 48 until Firefox 49, SVGs without viewport are displayed the same as SVGs with viewport, but if the slices are not exactly 50%, they are incorrectly stretched ([bug 1264809](https://bugzil.la/1264809)).", "Until Firefox 57, an issue persisted for SVGs without viewport when [e10s](https://wiki.mozilla.org/Electrolysis) was disabled ([bug 1290782](https://bugzil.la/1290782))."\]

14

6

1.0

## See also

- [Illustrated description of the 1-to-4-value syntax](shorthand_properties#tricky_edge_cases)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-slice" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-slice</a>
