# background-position

The `background-position` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the initial position for each background image. The position is relative to the position layer set by [`background-origin`](background-origin).

## Syntax

    /* Keyword values */
    background-position: top;
    background-position: bottom;
    background-position: left;
    background-position: right;
    background-position: center;

    /* <percentage> values */
    background-position: 25% 75%;

    /* <length> values */
    background-position: 0 0;
    background-position: 1cm 2cm;
    background-position: 10ch 8em;

    /* Multiple images */
    background-position: 0 0, center;

    /* Edge offsets values */
    background-position: bottom 10px right 20px;
    background-position: right 3em bottom 10px;
    background-position: bottom 10px right;
    background-position: top right 10px;

    /* Global values */
    background-position: inherit;
    background-position: initial;
    background-position: unset;

The `background-position` property is specified as one or more `<position>` values, separated by commas.

### Values

`<position>`  
A [`<position>`](position_value). A position defines an x/y coordinate, to place an item relative to the edges of an element's box. It can be defined using one to four values. If two non-keyword values are used, the first value represents the horizontal position and the second represents the vertical position. If only one value is specified, the second value is assumed to be `center`. If three or four values are used, the length-percentage values are offsets for the preceding keyword value(s).

**1-value syntax:** the value may be:

- The keyword value `center`, which centers the image.
- One of the keyword values `top`, `left`, `bottom`, `right`. This specifies an edge against which to place the item. The other dimension is then set to 50%, so the item is placed in the middle of the edge specified.
- A [`<length>`](length) or [`<percentage>`](percentage). This specifies the X coordinate relative to the left edge, with the Y coordinate set to 50%.

**2-value syntax:** one value defines X and the other defines Y. Each value may be:

- One of the keyword values `top`, `left`, `bottom`, `right`. If `left` or `right` are given here, then this defines X and the other given value defines Y. If `top` or `bottom` are given, then this defines Y and the other value defines X.
- A [`<length>`](length) or [`<percentage>`](percentage). If the other value is `left` or `right`, then this value defines Y, relative to the top edge. If the other value is `top` or `bottom`, then this value defines X, relative to the left edge. If both values are `<length>` or `<percentage>` values, then the first defines X and the second Y.
- Note that: If one value is `top` or `bottom`, then the other value may not be `top` or `bottom`. If one value is `left` or `right`, then the other value may not be `left` or `right`. This means, e.g., that `top top` and `left right` are not valid.
- The default value is `top left` or `0% 0%`.

**3-value syntax:** Two values are keyword values, and the third is the offset for the preceding value:

- The first value is one of the keyword values `top`, `left`, `bottom`, `right`, or `center`. If `left` or `right` are given here, then this defines X. If `top` or `bottom` are given, then this defines Y and the other keyword value defines X.
- The [`<length>`](length) or [`<percentage>`](percentage) value, if it is the second value, is the offset for the first value. If it is the third value, it is the offset for the second value.
- The single length or percentage value is an offset for the keyword value that precedes it. The combination of one keyword with two [`<length>`](length) or [`<percentage>`](percentage) values is not valid.

**4-value syntax:** The first and third values are keyword value defining X and Y. The second and fourth values are offsets for the preceding X and Y keyword values:

- The first value and third values one of the keyword values `top`, `left`, `bottom`, `right`. If `left` or `right` are given here, then this defines X. If `top` or `bottom` are given, then this defines Y and the other keyword value defines X.
- The second and fourth values are [`<length>`](length) or [`<percentage>`](percentage) values. The second value is the offset for the first keyword. The fourth value is the offset for the second keyword.

**Regarding Percentages:**

The percentage offset of the given background image's position is relative to the container. A value of 0% means that the left (or top) edge of the background image is aligned with the corresponding left (or top) edge of the container, or the 0% mark of the image will be on the 0% mark of the container. A value of 100% means that the _right_ (or _bottom_) edge of the background image is aligned with the _right_ (or _bottom_) edge of the container, or the 100% mark of the image will be on the 100% mark of the container. Thus a value of 50% horizontally or vertically centers the background image as the 50% of the image will be at the 50% mark of the container. Similarly, `background-position: 25% 75%` means the spot on the image that is 25% from the left and 75% from the top will be placed at the spot of the container that is 25% from the container's left and 75% from the container's top.

Essentially what happens is the background image dimension is _subtracted_ from the corresponding container dimension, and then a percentage of the resulting value is used as the direct offset from the left (or top) edge.

`(container width - image width) * (position x%) = (x offset value) (container height - image height) * (position y%) = (y offset value)`

Using the X axis for an example, let's say we have an image that is 300px wide and we are using it in a container that is 100px wide, with background-size set to auto:

`100px - 300px = -200px (container & image difference)`

So that with position percentages of -25%, 0%, 50%, 100%, 125%, we get these image-to-container edge offset values:

`-200px * -25% = 50px -200px * 0% = 0px -200px * 50% = -100px -200px * 100% = -200px`  
`-200px * 125% = -250px`

So with these resultant values for our example, the **left edge** of the **image** is offset from the **left edge** of the **container** by:

- \+ 50px (putting the left image edge in the center of the 100-pixel-wide container)
- 0px (left image edge coincident with the left container edge)
- -100px (left image edge 100px to the left of the container, in this example that means the middle 100px image area is centered in the container)
- -200px (left image edge 200px to the left of the container, in this example that means the right image edge is coincident with the right container edge)
- -250px (left image edge 250px to the left of the container, in this example that puts the right edge of the 300px-wide image in the center of the container)

It's worth mentioning that if your background-size is equal to the container size for a given axis, then a _percentage_ position for that axis will have no effect because the "container-image difference" will be zero. You will need to offset using absolute values.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0% 0%</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the size of the background positioning area minus size of background image; size refers to the width for horizontal offsets and to the height for vertical offsets</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="background-position-x"><code>background-position-x</code></a>: A list, each item consisting of: an offset given as a combination of an absolute length and a percentage, plus an origin keyword</li><li><a href="background-position-y"><code>background-position-y</code></a>: A list, each item consisting of: an offset given as a combination of an absolute length and a percentage, plus an origin keyword</li></ul></td></tr><tr class="even"><td>Animation type</td><td>repeatable list of simple list of length, percentage, or calc</td></tr></tbody></table>

## Formal syntax

    <bg-position>#where
    <bg-position> = [ [ left | center | right | top | bottom | <length-percentage> ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ] | [ center | [ left | right ] <length-percentage>? ] && [ center | [ top | bottom ] <length-percentage>? ] ]where
    <length-percentage> = <length> | <percentage>

## Examples

### Positioning background images

Each of these three examples uses the [`background`](background) property to create a yellow, rectangular element containing a star image. In each example, the star is in a different position. The third example illustrates how to specify positions for two different background images within one element.

#### HTML

    <div class="exampleone">Example One</div>
    <div class="exampletwo">Example Two</div>
    <div class="examplethree">Example Three</div>

#### CSS

    /* Shared among all <div>s */
    div {
      background-color: #FFEE99;
      background-repeat: no-repeat;
      width: 300px;
      height: 80px;
      margin-bottom: 12px;
    }

    /* These examples use the `background` shorthand property */
    .exampleone {
      background: url("https://mdn.mozillademos.org/files/11987/startransparent.gif") #FFEE99 2.5cm bottom no-repeat;
    }
    .exampletwo {
      background: url("https://mdn.mozillademos.org/files/11987/startransparent.gif") #FFEE99 left 4em bottom 1em no-repeat;
    }

    /* Multiple background images: Each image is matched with the
       corresponding position, from first specified to last. */
    .examplethree {
      background-image:    url("https://mdn.mozillademos.org/files/11987/startransparent.gif"),
                           url("https://mdn.mozillademos.org/files/7693/catfront.png");
      background-position: 0px 0px,
                           right 3em bottom 2em;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#background-position">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'background-position' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds support for multiple backgrounds and the four-value syntax. Modifies the percentage definition to match implementations.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/colors.html#propdef-background-position">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'background-position' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Allows for keyword values and <a href="length"><code>&lt;length&gt;</code></a> and <a href="percentage"><code>&lt;percentage&gt;</code></a> values to be mixed.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#background-position">CSS Level 1<br />
<span class="small">The definition of 'background-position' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`background-position`

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

`multiple_backgrounds`

1

12

3.6

9

10.5

1.3

≤37

18

4

14

1

1.0

`4_value_syntax`

25

12

13

9

10.5

7

≤37

25

14

14

7

1.5

### Quantum CSS notes

- Gecko has a bug meaning that `background-position` can't be [`transitioned`](transition) between two values containing different numbers of [`<position>`](position_value) values, for example `background-position: 10px 10px;` and `background-position: 20px 20px, 30px 30px;` (see [bug 1390446](https://bugzilla.mozilla.org/show_bug.cgi?id=1390446)). Firefox's new parallel CSS engine (also known as [Quantum CSS](https://wiki.mozilla.org/Quantum) or [Stylo](https://wiki.mozilla.org/Quantum/Stylo), planned for release in Firefox 57) fixes this.

## See also

- [`background-position-x`](background-position-x)
- [`background-position-y`](background-position-y)
- <span class="page-not-created">`background-position-inline`</span>
- <span class="page-not-created">`background-position-block`</span>
- [Using multiple backgrounds](css_backgrounds_and_borders/using_multiple_backgrounds)
- [`transform-origin`](transform-origin)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-position" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/background-position</a>
