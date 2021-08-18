# rotate

The `rotate` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property allows you to specify rotation transforms individually and independently of the [`transform`](transform) property. This maps better to typical user interface usage, and saves having to remember the exact order of transform functions to specify in the `transform` property.

## Syntax

    /* Keyword values */
    rotate: none;

    /* Angle value */
    rotate: 90deg;
    rotate: 0.25turn;
    rotate: 1.57rad;

    /* x, y, or z axis name plus angle */
    rotate: x 90deg;
    rotate: y 0.25turn;
    rotate: z 1.57rad;

    /* Vector plus angle value */
    rotate: 1 1 1 90deg;

### Values

angle value  
An [`<angle>`](angle) specifying the angle to rotate the affected element through, around the Z axis. Equivalent to a `rotate()` (2D rotation) function.

x, y, or z axis name plus angle value  
The name of the axis you want to rotate the affected element around (`"x"`, "`y`", or "`z"`), plus an [`<angle>`](angle) specifying the angle to rotate the element through. Equivalent to a `rotateX()`/`rotateY()`/`rotateZ()` (3D rotation) function.

vector plus angle value  
Three [`<number>`](number)s representing an origin-centered vector that defines a line around which you want to rotate the element, plus an [`<angle>`](angle) specifying the angle to rotate the element through. Equivalent to a `rotate3d()` (3D rotation) function.

`none`  
Specifies that no rotation should be applied.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>a transform</td></tr><tr class="even"><td>Creates <a href="css_positioning/understanding_z_index/the_stacking_context">stacking context</a></td><td>yes</td></tr></tbody></table>

## Formal syntax

    none | <angle> | [ x | y | z | <number>{3} ] && <angle>

## Examples

### Rotate an element on hover

#### HTML

    <div>
      <p class="rotate">Rotation</p>
    </div>

#### CSS

    .rotate {
      transition: rotate 1s;
    }

    div:hover .rotate {
      rotate: 1 -0.5 1 180deg;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#individual-transforms">CSS Transforms Level 2<br />
<span class="small">The definition of 'individual transforms' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`rotate`

No

No

72

60-72

No

No

14.1

No

No

60

No

14.5

No

`x_y_z_angle`

No

No

72

65-72

No

No

No

No

No

65

No

No

No

## See also

- [`translate`](translate)
- [`scale`](scale)
- [`transform`](transform)

Note: `skew` is not an independent `transform` value

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/rotate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/rotate</a>
