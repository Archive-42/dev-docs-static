# translate

The `translate` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property allows you to specify translation transforms individually and independently of the [`transform`](transform) property. This maps better to typical user interface usage, and saves having to remember the exact order of transform functions to specify in the `transform` value.

## Syntax

    /* Keyword values */
    translate: none;

    /* Single values */
    translate: 100px;
    translate: 50%;

    /* Two values */
    translate: 100px 200px;
    translate: 50% 105px;

    /* Three values */
    translate: 50% 105px 5rem;

### Values

Single [`<length-percentage>`](length-percentage) value  
A [`<length>`](length) or [`<percentage>`](percentage) that specifies a 2D translation, with the same translation along both the X and Y axes. Equivalent to a `translate()` (2D translation) function with a single value specified.

Two [`<length-percentage>`](length-percentage) values  
Two [`<length>`](length) or [`<percentage>`](percentage) that specify the X and Y axis translation values (respectively) of a 2D translation. Equivalent to a `translate()` (2D translation) function with two values specified.

Three values  
Two [`<length-percentage>`](length-percentage) and single [`<length>`](length) values that specify the X, Y, and Z axis translation values (respectively) of a 3D translation. Equivalent to a `translate3d()` (3D translation) function.

`none`  
Specifies that no translation should be applied.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the size of bounding box</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr><tr class="even"><td>Animation type</td><td>a transform</td></tr><tr class="odd"><td>Creates <a href="css_positioning/understanding_z_index/the_stacking_context">stacking context</a></td><td>yes</td></tr></tbody></table>

## Formal syntax

    none | <length-percentage> [ <length-percentage> <length>? ]?where
    <length-percentage> = <length> | <percentage>

## Examples

### HTML

    <div>
      <p class="translate">Translation</p>
    </div>

### CSS

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

    .translate {
      transition: translate 1s;
    }

    div:hover .translate {
      translate: 200px 50px;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#individual-transforms">CSS Transforms Level 2<br />
<span class="small">The definition of 'individual transforms' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the size of bounding box</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr><tr class="even"><td>Animation type</td><td>a transform</td></tr><tr class="odd"><td>Creates <a href="css_positioning/understanding_z_index/the_stacking_context">stacking context</a></td><td>yes</td></tr></tbody></table>

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

`translate`

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

- [`scale`](scale)
- [`rotate`](rotate)
- [`transform`](transform)

Note: skew is not an independent transform value

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/translate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/translate</a>
