# scale

The `scale` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property allows you to specify scale transforms individually and independently of the [`transform`](transform) property. This maps better to typical user interface usage, and saves having to remember the exact order of transform functions to specify in the `transform` value.

## Syntax

    /* Keyword values */
    scale: none;

    /* Single values */
    /* values of more than 1 make the element grow */
    scale: 2;
    /* values of less than 1 make the element shrink */
    scale: 0.5;

    /* Two values */
    scale: 2 0.5;

    /* Three values */
    scale: 2 0.5 2;

### Values

Single number value  
A [`<number>`](number) specifying a scale factor to make the affected element scale by the same factor along both the X and Y axes. Equivalent to a `scale()` (2D scaling) function with a single value specified.

Two length/percentage values  
Two [`<number>`](number)s that specify the X and Y axis scaling values (respectively) of a 2D scale. Equivalent to a `scale()` (2D scaling) function with two values specified.

Three length/percentage values  
Three [`<number>`](number)s that specify the X, Y, and Z axis scaling values (respectively) of a 3D scale. Equivalent to a `scale3d()` (3D scaling) function.

`none`  
Specifies that no scaling should be applied.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>a transform</td></tr><tr class="even"><td>Creates <a href="css_positioning/understanding_z_index/the_stacking_context">stacking context</a></td><td>yes</td></tr></tbody></table>

## Formal syntax

    none | <number>{1,3}

## Examples

### Scaling an element on hover

#### HTML

    <div>
      <p class="scale">Scaling</p>
    </div>

#### CSS

    * {
      box-sizing: border-box;
    }

    html {
      font-family: sans-serif;
    }

    div {
      width: 150px;
      margin: 0 auto;
    }

    p {
      padding: 10px 5px;
      border: 3px solid black;
      border-radius: 20px;
      width: 150px;
      font-size: 1.2rem;
      text-align: center;
    }

    .scale {
      transition: scale 1s;
    }

    div:hover .scale {
      scale: 2 0.7;
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

`scale`

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

## See also

- [`translate`](translate)
- [`rotate`](rotate)
- [`transform`](transform)

Note: skew is not an independent transform value

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scale" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scale</a>
