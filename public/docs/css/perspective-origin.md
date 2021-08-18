# perspective-origin

The `perspective-origin` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property determines the position at which the viewer is looking. It is used as the _vanishing point_ by the [`perspective`](perspective) property.

The `perspective-origin` and [`perspective`](perspective) properties are attached to the parent of a child transformed in 3-dimensional space, unlike the `perspective()` transform function which is placed on the element being transformed.

## Syntax

    /* One-value syntax */
    perspective-origin: x-position;

    /* Two-value syntax */
    perspective-origin: x-position y-position;

    /* When both x-position and y-position are keywords,
       the following is also valid */
    perspective-origin: y-position x-position;

    /* Global values */
    perspective-origin: inherit;
    perspective-origin: initial;
    perspective-origin: unset;

### Values

_x-position_  
Indicates the position of the abscissa of the _vanishing point_. It can have one of the following values:

- [`<length-percentage>`](length-percentage) indicating the position as an absolute length value or relative to the width of the element. The value may be negative.
- `left`, a keyword being a shortcut for the `0` length value.
- `center`, a keyword being a shortcut for the `50%` percentage value.
- `right`, a keyword being a shortcut for the `100%` percentage value.

_y-position_  
Indicates the position of the ordinate of the _vanishing point_. It can have one of the following values:

- [`<length-percentage>`](length-percentage) indicating the position as an absolute length value or relative to the height of the element. The value may be negative.
- `top`, a keyword being a shortcut for the `0` length value.
- `center`, a keyword being a shortcut for the `50%` percentage value.
- `bottom`, a keyword being a shortcut for the `100%` percentage value.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>50% 50%</code></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the size of bounding box</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>for <a href="length"><code>&lt;length&gt;</code></a> the absolute value, otherwise a percentage</td></tr><tr class="even"><td>Animation type</td><td>simple list of length, percentage, or calc</td></tr></tbody></table>

## Formal syntax

    <position>where
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]where
    <length-percentage> = <length> | <percentage>

## Examples

### Changing the perspective origin

This example shows cubes with popular `perspective-origin` values.

#### HTML

    <section>

    <figure>
      <figcaption><code>perspective-origin: top left;</code></figcaption>
        <div class="container">
         <div class="cube potl">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
         </div>
        </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: top;</code></figcaption>
       <div class="container">
        <div class="cube potm">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: top right;</code></figcaption>
      <div class="container">
        <div class="cube potr">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: left;</code></figcaption>
      <div class="container">
        <div class="cube poml">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: 50% 50%;</code></figcaption>
      <div class="container">
        <div class="cube pomm">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: right;</code></figcaption>
      <div class="container">
        <div class="cube pomr">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: bottom left;</code></figcaption>
      <div class="container">
        <div class="cube pobl">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: bottom;</code></figcaption>
      <div class="container">
        <div class="cube pobm">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: bottom right;</code></figcaption>
      <div class="container">
        <div class="cube pobr">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: -200% -200%;</code></figcaption>
      <div class="container">
        <div class="cube po200200neg">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: 200% 200%;</code></figcaption>
      <div class="container">
        <div class="cube po200200pos">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: 200% -200%;</code></figcaption>
      <div class="container">
        <div class="cube po200200">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    </section>

#### CSS

    /* perspective-origin values (unique per example) */
    .potl {
      perspective-origin: top left;
    }
    .potm {
      perspective-origin: top;
    }
    .potr {
      perspective-origin: top right;
    }
    .poml {
      perspective-origin: left;
    }
    .pomm {
      perspective-origin: 50% 50%;
    }
    .pomr {
      perspective-origin: right;
    }
    .pobl {
      perspective-origin: bottom left;
    }
    .pobm {
      perspective-origin: bottom;
    }
    .pobr {
      perspective-origin: bottom right;
    }
    .po200200neg {
      perspective-origin: -200% -200%;
    }
    .po200200pos {
      perspective-origin: 200% 200%;
    }
    .po200200 {
      perspective-origin: 200% -200%;
    }

    /* Define the container div, the cube div, and a generic face */
    .container {
      width: 100px;
      height: 100px;
      margin: 24px;
      border: none;
    }

    .cube {
      width: 100%;
      height: 100%;
      backface-visibility: visible;
      perspective: 300px;
      transform-style: preserve-3d;
    }

    .face {
      display: block;
      position: absolute;
      width: 100px;
      height: 100px;
      border: none;
      line-height: 100px;
      font-family: sans-serif;
      font-size: 60px;
      color: white;
      text-align: center;
    }

    /* Define each face based on direction */
    .front {
      background: rgba(0, 0, 0, 0.3);
      transform: translateZ(50px);
    }
    .back {
      background: rgba(0, 255, 0, 1);
      color: black;
      transform: rotateY(180deg) translateZ(50px);
    }
    .right {
      background: rgba(196, 0, 0, 0.7);
      transform: rotateY(90deg) translateZ(50px);
    }
    .left {
      background: rgba(0, 0, 196, 0.7);
      transform: rotateY(-90deg) translateZ(50px);
    }
    .top {
      background: rgba(196, 196, 0, 0.7);
      transform: rotateX(90deg) translateZ(50px);
    }
    .bottom {
      background: rgba(196, 0, 196, 0.7);
      transform: rotateX(-90deg) translateZ(50px);
    }

    /* Make the layout a little nicer */
    section {
      background-color: #EEE;
      padding: 10px;
      font-family: sans-serif;
      text-align: left;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#perspective-origin-property">CSS Transforms Level 2<br />
<span class="small">The definition of 'perspective-origin' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`perspective-origin`

36

12

12

12

16

10

49

45

10

23

15

9

4

37

3

36

18

16

10

49

45

24

14

9

2

3.0

1.0

`three_value_syntax`

36-68

12

12-79

12

16-70

10

49

45

10

15-55

9

4

37-68

3

36-68

18

16

10

49

45

14-48

9

2

3.0-10.0

1.0

## See also

- [Using CSS Transforms](css_transforms/using_css_transforms)
- [`transform-style`](transform-style)
- [`<transform-function>`](transform-function)
- [`perspective`](perspective)
- `transform: perspective()` function

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/perspective-origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/perspective-origin</a>
