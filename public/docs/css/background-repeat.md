# background-repeat

The `background-repeat` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how background images are repeated. A background image can be repeated along the horizontal and vertical axes, or not repeated at all.

By default, the repeated images are clipped to the size of the element, but they can be scaled to fit (using `round`) or evenly distributed from end to end (using `space`).

## Syntax

    /* Keyword values */
    background-repeat: repeat-x;
    background-repeat: repeat-y;
    background-repeat: repeat;
    background-repeat: space;
    background-repeat: round;
    background-repeat: no-repeat;

    /* Two-value syntax: horizontal | vertical */
    background-repeat: repeat space;
    background-repeat: repeat repeat;
    background-repeat: round space;
    background-repeat: no-repeat round;

    /* Global values */
    background-repeat: inherit;
    background-repeat: initial;
    background-repeat: unset;

### Values

`<repeat-style>`  
The one-value syntax is a shorthand for the full two-value syntax:

<table><tbody><tr class="odd"><td><strong>Single value</strong></td><td><strong>Two-value equivalent</strong></td></tr><tr class="even"><td><code>repeat-x</code></td><td><code>repeat no-repeat</code></td></tr><tr class="odd"><td><code>repeat-y</code></td><td><code>no-repeat repeat</code></td></tr><tr class="even"><td><code>repeat</code></td><td><code>repeat repeat</code></td></tr><tr class="odd"><td><code>space</code></td><td><code>space space</code></td></tr><tr class="even"><td><code>round</code></td><td><code>round round</code></td></tr><tr class="odd"><td><code>no-repeat</code></td><td><code>no-repeat no-repeat</code></td></tr></tbody></table>

In the two-value syntax, the first value represents the horizontal repetition behavior and the second value represents the vertical behavior. Here is an explanation of how each option works for either direction:

<table><tbody><tr class="odd"><td><code>repeat</code></td><td>The image is repeated as much as needed to cover the whole background image painting area. The last image will be clipped if it doesn't fit.</td></tr><tr class="even"><td><code>space</code></td><td>The image is repeated as much as possible without clipping. The first and last images are pinned to either side of the element, and whitespace is distributed evenly between the images. The <a href="background-position"><code>background-position</code></a> property is ignored unless only one image can be displayed without clipping. The only case where clipping happens using <code>space</code> is when there isn't enough room to display one image.</td></tr><tr class="odd"><td><code>round</code></td><td>As the allowed space increases in size, the repeated images will stretch (leaving no gaps) until there is room (space left &gt;= half of the image width) for another one to be added. When the next image is added, all of the current ones compress to allow room. Example: An image with an original width of 260px, repeated three times, might stretch until each repetition is 300px wide, and then another image will be added. They will then compress to 225px.</td></tr><tr class="even"><td><code>no-repeat</code></td><td>The image is not repeated (and hence the background image painting area will not necessarily be entirely covered). The position of the non-repeated background image is defined by the <a href="background-position"><code>background-position</code></a> CSS property.</td></tr></tbody></table>

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>repeat</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>a list, each item consisting of two keywords, one per dimension</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <repeat-style>#where
    <repeat-style> = repeat-x | repeat-y | [ repeat | space | round | no-repeat ]{1,2}

## Examples

### Setting background-repeat

#### HTML

    <ol>
      <li>no-repeat
        <div class="one"></div>
      </li>
      <li>repeat
        <div class="two"></div>
      </li>
      <li>repeat-x
        <div class="three"></div>
      </li>
      <li>repeat-y
        <div class="four"></div>
      </li>
      <li>space
        <div class="five"></div>
      </li>
      <li>round
        <div class="six"></div>
      </li>
      <li>repeat-x, repeat-y (multiple images)
        <div class="seven"></div>
      </li>
    </ol>

#### CSS

    /* Shared for all DIVS in example */
    ol,
    li {
      margin: 0;
      padding: 0;
    }
    li {
      margin-bottom: 12px;
    }
    div {
        background-image: url(https://mdn.mozillademos.org/files/12005/starsolid.gif);
        width: 160px;
        height: 70px;
    }

    /* Background repeats */
    .one {
      background-repeat: no-repeat;
    }
    .two {
      background-repeat: repeat;
    }
    .three {
      background-repeat: repeat-x;
    }
    .four {
      background-repeat: repeat-y;
    }
    .five {
      background-repeat: space;
    }
    .six {
      background-repeat: round;
    }

    /* Multiple images */
    .seven {
      background-image:  url(https://mdn.mozillademos.org/files/12005/starsolid.gif),
                         url(https://developer.mozilla.org/static/img/favicon32.png);
      background-repeat: repeat-x,
                         repeat-y;
      height: 144px;
    }

#### Result

In this example, each list item is matched with a different value of `background-repeat`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-background-repeat">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'background-repeat' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds support for multiple background images, the two-value syntax allowing distinct repetition behavior for the horizontal and vertical directions, the <code>space</code> and <code>round</code> keywords, and for backgrounds on inline-level elements by precisely defining the background painting area.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/colors.html#propdef-background-repeat">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'background-repeat' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant changes.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#background-repeat">CSS Level 1<br />
<span class="small">The definition of 'background-repeat' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`background-repeat`

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

`multiple_backgrounds`

1

12

3.6

9

10.5

1.3

1

18

4

11

1

1.0

`round_space`

30

12

49

9

17

10.5-15

7

4.4

30

49

18

8

2.0

`2-value`

3

12

13

9

10.5

5

≤37

18

14

11

4

1.0

## See also

- [Using multiple backgrounds](css_backgrounds_and_borders/using_multiple_backgrounds)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-repeat" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/background-repeat</a>
