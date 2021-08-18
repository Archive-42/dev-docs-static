# offset-distance

The `offset-distance` CSS property specifies a position along an [`offset-path`](offset-path) for an element to be placed.

## Syntax

    /* Default value */
    offset-distance: 0;

    /* the middle of the offset-path */
    offset-distance: 50%;

    /* a fixed length positioned along the path */
    offset-distance: 40px;

`<length-percentage>`  
A length that specifies how far the element is along the path (defined with [`offset-path`](offset-path)).

100% represents the total length of the path (when the `offset-path` is defined as a basic shape or `path()`).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the total path length</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>for <a href="length"><code>&lt;length&gt;</code></a> the absolute value, otherwise a percentage</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <length-percentage>where
    <length-percentage> = <length> | <percentage>

## Examples

### Using offset-distance in an animation

The motion aspect in CSS Motion Path typically comes from animating the `offset-distance` property. If you want to animate an element along its full path, you would define its [`offset-path`](offset-path) and then set up an animation that takes the `offset-distance` from `0%` to `100%`.

#### HTML

    <div id="motion-demo"></div>

#### CSS

    #motion-demo {
      offset-path: path('M20,20 C20,100 200,0 200,100');
      animation: move 3000ms infinite alternate ease-in-out;
      width: 40px;
      height: 40px;
      background: cyan;
    }

    @keyframes move {
      0% {
        offset-distance: 0%;
      }
      100% {
        offset-distance: 100%;
      }
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/motion-1/#offset-distance-property">Motion Path Module Level 1<br />
<span class="small">The definition of 'offset-distance' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`offset-distance`

55

46

79

79

72

69-72

No

42

33

No

55

46

55

46

No

42

33

No

6.0

5.0

## See also

- [`offset`](offset)
- [`offset-anchor`](offset-anchor)
- [`offset-path`](offset-path)
- [`offset-position`](offset-position)
- [`offset-rotate`](offset-rotate)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/offset-distance" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/offset-distance</a>
