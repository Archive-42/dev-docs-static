# offset-path

The `offset-path` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies a motion path for an element to follow and defines the element's positioning within the parent container or SVG coordinate system.

## Syntax

    /* Default */
    offset-path: none;

    /* Function values */
    offset-path: ray(45deg closest-side contain);

    /* URL */
    offset-path: url(#path);

    /* Shapes */
    offset-path: circle(50% at 25% 25%);
    offset-path: inset(50% 50% 50% 50%);
    offset-path: polygon(30% 0%, 70% 0%, 100% 50%, 30% 100%, 0% 70%, 0% 30%);
    offset-path: path('M 0,200 Q 200,200 260,80 Q 290,20 400,0 Q 300,100 400,200');

    /* Geometry Boxes */
    offset-path: margin-box;
    offset-path: stroke-box;

    /* Global values */
    offset-path: inherit;
    offset-path: initial;
    offset-path: unset;

### Values

`ray()`  
Taking up to three values, defines a path that is a line segment starting from the position of the box and proceeds in the direction defined by the specified angle similar to the CSS gradient angle where `0deg` is up, with positive angles increasing in the clockwise direction, with the size value being similar to the CSS radial gradient size values from `closest-side` to `farthest-corner`, and the keyterm `contain`.

`url()`  
References the ID of an SVG shape -- `circle`, `ellipse`, `line`, `path`, `polygon`, `polyline`, or `rect` -- using the shape's geometry as the path.

`<basic-shape>`  
Specifies a [CSS shape](css_shapes/basic_shapes) including `circle()`, `ellipse()`, `inset()`, `polygon()`, or `path()`.

`path()`  
A path string defined with SVG coordinate syntax.

`none`  
Specifies no motion path at all.

## Description

This property defines a path an animated element can follow. An offset path is either a specified path with one or multiple sub-paths or the geometry of a not-styled basic shape. The element’s exact position on the offset path is determined by the [`offset-distance`](offset-distance) property. Each shape or path must define an initial position for the computed value of `0` for [`offset-distance`](offset-distance) and an initial direction which specifies the rotation of the object to the initial position.

Early versions of the spec called this property `motion-path`. It was changed to `offset-path` because the property describes static positions, not motion.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>as &lt;angle&gt;, &lt;basic-shape&gt; or &lt;path()&gt;</td></tr><tr class="even"><td>Creates <a href="css_positioning/understanding_z_index/the_stacking_context">stacking context</a></td><td>yes</td></tr></tbody></table>

## Formal syntax

    none | ray( [ <angle> && <size> && contain? ] ) | <path()> | <url> | [ <basic-shape> || <geometry-box> ]where
    <size> = closest-side | farthest-side | closest-corner | farthest-corner | <length> | <length-percentage>{2}
    <path()> = path( [ <fill-rule>, ]? <string> )
    <basic-shape> = <inset()> | <circle()> | <ellipse()> | <polygon()> | <path()>
    <geometry-box> = <shape-box> | fill-box | stroke-box | view-boxwhere
    <length-percentage> = <length> | <percentage>
    <fill-rule> = nonzero | evenodd
    <inset()> = inset( <length-percentage>{1,4} [ round <'border-radius'> ]? )
    <circle()> = circle( [ <shape-radius> ]? [ at <position> ]? )
    <ellipse()> = ellipse( [ <shape-radius>{2} ]? [ at <position> ]? )
    <polygon()> = polygon( <fill-rule>? , [ <length-percentage> <length-percentage> ]# )
    <shape-box> = <box> | margin-boxwhere
    <shape-radius> = <length-percentage> | closest-side | farthest-side
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]
    <box> = border-box | padding-box | content-box

## Examples

### Animating an element with offset-path

The `offset-path` properties in the CSS code sample defines a motion path that is identical to the `<path>` element in the SVG. The path, as can be seen in the rendering of the SVG code, is a line drawing of a house with a chimney.

#### SVG

The top and bottom halves of the scissors would appear in the top left of the canvas were they not positioned along the starting point of the motion path defined by `offset-path`.

    <svg xmlns="http://www.w3.org/2000/svg"
         width="700"
         height="450"
         viewBox="350 0 1400 900">
      <title>House and Scissors</title>
      <rect x="595"
            y="423"
            width="610"
            height="377"
            fill="blue" />
      <polygon points="506,423 900,190 1294,423"
               fill="yellow" />
      <polygon points="993,245 993,190 1086,190 1086,300"
               fill="red" />
      <path id="house" d="M900,190 L993,245 V201 A11,11 0 0,1 1004,190 H1075 A11,11 0 0,1 1086,201 V300 L1294,423 H1216 A11,11 0 0,0 1205,434 V789 A11,11 0 0,1 1194,800 H606 A11,11 0 0,1 595,789 V434 A11,11 0 0,0 584,423 H506 L900,190"
            fill="none"
            stroke="black"
            stroke-width="13"
            stroke-linejoin="round"
            stroke-linecap="round" />
      <path id="firstScissorHalf" class="scissorHalf"
            d="M30,0 H-10 A10,10 0 0,0 -20,10 A20,20 0 1,1 -40,-10 H20 A10,10 0 0,1 30,0 M-40,20 A10,10 1 0,0 -40,0 A10,10 1 0,0 -40,20 M0,0"
            transform="translate(0,0)"
            fill="green"
            stroke="black"
            stroke-width="5"
            stroke-linejoin="round"
            stroke-linecap="round"
            fill-rule="evenodd" />
      <path id="secondScissorHalf" class="scissorHalf"
            d="M30,0 H-10 A10,10 0 0,1 -20,-10 A20,20 0 1,0 -40,10 H20 A10,10 0 0,0 30,0 M-40,-20 A10,10 1 0,0 -40,0 A10,10 1 0,0 -40,-20 M0,0"
            transform="translate(0,0)"
            fill="forestgreen"
            stroke="black"
            stroke-width="5"
            stroke-linejoin="round"
            stroke-linecap="round"
            fill-rule="evenodd" />
    </svg>

#### CSS

    .scissorHalf {
      offset-path: path('M900,190  L993,245 V201  A11,11 0 0,1 1004,190  H1075  A11,11 0 0,1 1086,201  V300  L1294,423 H1216  A11,11 0 0,0 1205,434  V789  A11,11 0 0,1 1194,800  H606  A11,11 0 0,1 595,789  V434  A11,11 0 0,0 584,423  H506 L900,190');
      animation: followpath 4s linear infinite;
    }

    @keyframes followpath {
       to {
         motion-offset: 100%;
         offset-distance: 100%;
       }
    }

#### Result

## Specifications

&lt;body&gt;

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/motion-1/#offset-path-property">Motion Path Module Level 1<br />
<span class="small">The definition of 'offset-path' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`offset-path`

55

46

79

79

72

63-72

No

45

32

No

55

46

55

46

63

43

32

No

6.0

`path()` is the only value type supported.

5.0

`path-support`

64

79

63

No

51

No

64

64

63

47

No

9.0

`ray-support`

64

79

71

No

51

No

64

64

No

47

No

9.0

## See also

- [`offset`](offset)
- [`offset-distance`](offset-distance)
- [`offset-rotation`](offset-rotate)
- [SVG &lt;path&gt;](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths)

Other demos:

- [Examples of the various values](https://codepen.io/team/css-tricks/pen/WZdKMq)
- [Triangle](https://codepen.io/ericwilligers/pen/jrbJPp)
- [Scissors](https://codepen.io/ericwilligers/pen/bwVkNa)
- [Eyes](https://jsfiddle.net/ericwilligers/r1snqdan/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/offset-path" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/offset-path</a>
