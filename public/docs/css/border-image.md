# border-image

The `border-image` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property draws an image around a given element. It replaces the element's regular [border](border).

**Note:** You should specify a separate [`border-style`](border-style) in case the border image fails to load. Indeed, this is required according to the specification, although not all browsers implement this requirement.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`border-image-outset`](border-image-outset)
- [`border-image-repeat`](border-image-repeat)
- [`border-image-slice`](border-image-slice)
- [`border-image-source`](border-image-source)
- [`border-image-width`](border-image-width)

## Syntax

    /* source | slice */
    border-image: linear-gradient(red, blue) 27;

    /* source | slice | repeat */
    border-image: url("/images/border.png") 27 space;

    /* source | slice | width */
    border-image: linear-gradient(red, blue) 27 / 35px;

    /* source | slice | width | outset | repeat */
    border-image: url("/images/border.png") 27 23 / 50px 30px / 1rem round space;

The `border-image` property may be specified with anywhere from one to five of the values listed below.

**Note:** If the [computed value](computed_value) of [`border-image-source`](border-image-source) is `none`, or if the image cannot be displayed, the [`border-style`](border-style) will be displayed instead.

### Values

`<'border-image-source'>`  
The source image. See [`border-image-source`](border-image-source).

`<'border-image-slice'>`  
The dimensions for slicing the source image into regions. Up to four values may be specified. See [`border-image-slice`](border-image-slice).

`<'border-image-width'>`  
The width of the border image. Up to four values may be specified. See [`border-image-width`](border-image-width).

`<'border-image-outset'>`  
The distance of the border image from the element's outside edge. Up to four values may be specified. See [`border-image-outset`](border-image-outset).

`<'border-image-repeat'>`  
Defines how the edge regions of the source image are adjusted to fit the dimensions of the border image. Up to two values may be specified. See [`border-image-repeat`](border-image-repeat).

## Accessibility concerns

Assistive technology cannot parse border images. If the image contains information critical to understanding the page's overall purpose, it is better to describe it semantically in the document.

- [MDN Understanding WCAG, Guideline 1.1 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%e2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 | Understanding WCAG 2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/text-equiv-all.html)

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-image-source"><code>border-image-source</code></a>: <code>none</code></li><li><a href="border-image-slice"><code>border-image-slice</code></a>: <code>100%</code></li><li><a href="border-image-width"><code>border-image-width</code></a>: <code>1</code></li><li><a href="border-image-outset"><code>border-image-outset</code></a>: <code>0</code></li><li><a href="border-image-repeat"><code>border-image-repeat</code></a>: <code>stretch</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements, except internal table elements when <a href="border-collapse"><code>border-collapse</code></a> is <code>collapse</code>. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-image-slice"><code>border-image-slice</code></a>: refer to the size of the border image</li><li><a href="border-image-width"><code>border-image-width</code></a>: refer to the width or height of the border image area</li></ul></td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-image-outset"><code>border-image-outset</code></a>: as specified, but with relative lengths converted into absolute lengths</li><li><a href="border-image-repeat"><code>border-image-repeat</code></a>: as specified</li><li><a href="border-image-slice"><code>border-image-slice</code></a>: one to four percentage(s) (as specified) or absolute length(s), plus the keyword <code>fill</code> if specified</li><li><a href="border-image-source"><code>border-image-source</code></a>: <code>none</code> or the image with its URI made absolute</li><li><a href="border-image-width"><code>border-image-width</code></a>: as specified, but with relative lengths converted into absolute lengths</li></ul></td></tr><tr class="even"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <'border-image-source'> || <'border-image-slice'> [ / <'border-image-width'> | / <'border-image-width'>? / <'border-image-outset'> ]? || <'border-image-repeat'>

## Examples

### Bitmap

In this example, we will apply a diamond pattern to an element's borders. The source for the border image is a ".png" file of 81 by 81 pixels, with three diamonds going vertically and horizontally:

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFEAAABRBAMAAABYoVcFAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAbUExURUdwTP+9W/9OAP++XP9LAP9MAP++XP++XP9MAOhuzeIAAAAHdFJOUwAnJ+bmzMyXyojtAAABQElEQVRIx+2WMW7DMAxF5ZzAgIDMKZAeQFP2TBkzBR3bqQcIUF6gg44dWZZFfgEEyCGbtQlP/8GWSEEh1PF5CjymHzFBFA63q5jF56yhcM7/nJwulBRUcjlzMhKxFFHJZU4WJbEUUM1xsihZiqjmerIquxRQy23JqtykiFquJZuySQH13JpsylWKqOdqsiurFJDILcmuXKSIRK4kP1hZpIBO4UtM80MspD9Ad4fT/p32f3fsp/2MHOduryVHfdpr3tFH9t509Lv9DgnHOWgD0XRJ2sIBRXpqUkTLFiZNCSgSaVJE61EnTSlQJNKkiLaSTJqyo0ikSRFx6yRN2VAk0qSIRDeO0gGJDh+lA/qVF8w3rByQ3Wn/Tvu/O/bTfkaOc7fXkqM+7TXv6CN7bzr63X6H7G+b/W2zv232t8273zYvbLa23TXqfm0AAAAASUVORK5CYII=" alt="an example borderimage" width="81" height="81" />

#### HTML

    <div id="bitmap">This element is surrounded by a bitmap-based border image!</div>

#### CSS

To match the size of a single diamond, we will use a value of 81 divided by 3, or `27`, for slicing the image into corner and edge regions. To center the border image on the edge of the element's background, we will make the outset values equal to half of the width values. Finally, a repeat value of `round` will make the border slices fit evenly, i.e., without clipping or gaps.

    #bitmap {
      width: 200px;
      background-color: #ffa;
      border: 36px solid orange;
      margin: 30px;
      padding: 10px;

      border-image:
          url("https://mdn.mozillademos.org/files/4127/border.png")  /* source */
          27 /                    /* slice */
          36px 28px 18px 8px /    /* width */
          18px 14px 9px 4px       /* outset */
          round;                  /* repeat */
    }

#### Result

### Gradient

#### HTML

    <div id="gradient">This element is surrounded by a gradient-based border image!</div>

#### CSS

    #gradient {
      width: 200px;
      border: 30px solid;
      border-image: repeating-linear-gradient(45deg, #f33, #3bf, #f33 30px) 60;
      padding: 20px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-border-image">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-image' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-image-source"><code>border-image-source</code></a>: <code>none</code></li><li><a href="border-image-slice"><code>border-image-slice</code></a>: <code>100%</code></li><li><a href="border-image-width"><code>border-image-width</code></a>: <code>1</code></li><li><a href="border-image-outset"><code>border-image-outset</code></a>: <code>0</code></li><li><a href="border-image-repeat"><code>border-image-repeat</code></a>: <code>stretch</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements, except internal table elements when <a href="border-collapse"><code>border-collapse</code></a> is <code>collapse</code>. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-image-slice"><code>border-image-slice</code></a>: refer to the size of the border image</li><li><a href="border-image-width"><code>border-image-width</code></a>: refer to the width or height of the border image area</li></ul></td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-image-outset"><code>border-image-outset</code></a>: as specified, but with relative lengths converted into absolute lengths</li><li><a href="border-image-repeat"><code>border-image-repeat</code></a>: as specified</li><li><a href="border-image-slice"><code>border-image-slice</code></a>: one to four percentage(s) (as specified) or absolute length(s), plus the keyword <code>fill</code> if specified</li><li><a href="border-image-source"><code>border-image-source</code></a>: <code>none</code> or the image with its URI made absolute</li><li><a href="border-image-width"><code>border-image-width</code></a>: as specified, but with relative lengths converted into absolute lengths</li></ul></td></tr><tr class="even"><td>Animation type</td><td>discrete</td></tr></tbody></table>

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

`border-image`

16

7

12

12

15

\["Small SVGs are incorrectly stretched, because percentages in [`border-image-slice`](https://developer.mozilla.org/docs/Web/CSS/border-image-slice) are computed to integers instead of floats ([bug 1284797](https://bugzil.la/1284797)).", "Until Firefox 47, SVGs without viewport were not sliced correctly ([bug 619500](https://bugzil.la/619500)).", "From Firefox 48 until Firefox 49, SVGs without viewport are displayed the same as SVGs with viewport, but if the slices are not exactly 50%, they are incorrectly stretched ([bug 1264809](https://bugzil.la/1264809)).", "Until Firefox 57, an issue persisted for SVGs without viewport when [e10s](https://wiki.mozilla.org/Electrolysis) was disabled ([bug 1290782](https://bugzil.la/1290782))."\]

3.5

An earlier version of the specification was implemented, prefixed, in Firefox versions prior to 15.

44

11

11

10.5-15

6

3

≤37

2

18

18

15

\["Small SVGs are incorrectly stretched, because percentages in [`border-image-slice`](https://developer.mozilla.org/docs/Web/CSS/border-image-slice) are computed to integers instead of floats ([bug 1284797](https://bugzil.la/1284797)).", "Until Firefox 47, SVGs without viewport were not sliced correctly ([bug 619500](https://bugzil.la/619500)).", "From Firefox 48 until Firefox 49, SVGs without viewport are displayed the same as SVGs with viewport, but if the slices are not exactly 50%, they are incorrectly stretched ([bug 1264809](https://bugzil.la/1264809)).", "Until Firefox 57, an issue persisted for SVGs without viewport when [e10s](https://wiki.mozilla.org/Electrolysis) was disabled ([bug 1290782](https://bugzil.la/1290782))."\]

4

An earlier version of the specification was implemented, prefixed, in Firefox versions prior to 15.

44

11

11-14

6

3.2

1.0

1.0

`fill`

16

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

`gradient`

7

12

29

11

15

4

≤37

18

29

14

3.2

1.0

`optional_border_image_slice`

16

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

- [`border`](border)
- [`outline`](outline)
- [`box-shadow`](box-shadow)
- [`background-image`](background-image)
- [`url()`](<url()>) function
- Gradient functions: [`conic-gradient()`](<conic-gradient()>), [`linear-gradient()`](<linear-gradient()>), [`repeating-linear-gradient()`](<repeating-linear-gradient()>), [`radial-gradient()`](<radial-gradient()>), [`repeating-radial-gradient()`](<repeating-radial-gradient()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-image" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-image</a>
