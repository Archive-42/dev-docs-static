# offset

The `offset` CSS [shorthand property](shorthand_properties) sets all the properties required for animating an element along a defined path.

**Note**: Early versions of the spec called this property `motion`.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`offset-anchor`](offset-anchor)
- [`offset-distance`](offset-distance)
- [`offset-path`](offset-path)
- [`offset-position`](offset-position)
- [`offset-rotate`](offset-rotate)

## Syntax

    /* Offset position */
    offset: auto;
    offset: 10px 30px;
    offset: none;

    /* Offset path */
    offset: ray(45deg closest-side);
    offset: path('M 100 100 L 300 100 L 200 300 z');
    offset: url(arc.svg);

    /* Offset path with distance and/or rotation */
    offset: url(circle.svg) 100px;
    offset: url(circle.svg) 40%;
    offset: url(circle.svg) 30deg;
    offset: url(circle.svg) 50px 20deg;

    /* Including offset anchor */
    offset: ray(45deg closest-side) / 40px 20px;
    offset: url(arc.svg) 2cm / 0.5cm 3cm;
    offset: url(arc.svg) 30deg / 50px 100px;

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="offset-position"><code>offset-position</code></a>: <code>auto</code></li><li><a href="offset-path"><code>offset-path</code></a>: <code>none</code></li><li><a href="offset-distance"><code>offset-distance</code></a>: <code>0</code></li><li><a href="offset-anchor"><code>offset-anchor</code></a>: <code>auto</code></li><li><a href="offset-rotate"><code>offset-rotate</code></a>: <code>auto</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="offset-position"><code>offset-position</code></a>: referToSizeOfContainingBlock</li><li><a href="offset-distance"><code>offset-distance</code></a>: refer to the total path length</li><li><a href="offset-anchor"><code>offset-anchor</code></a>: relativeToWidthAndHeight</li></ul></td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="offset-position"><code>offset-position</code></a>: for <a href="length"><code>&lt;length&gt;</code></a> the absolute value, otherwise a percentage</li><li><a href="offset-path"><code>offset-path</code></a>: as specified</li><li><a href="offset-distance"><code>offset-distance</code></a>: for <a href="length"><code>&lt;length&gt;</code></a> the absolute value, otherwise a percentage</li><li><a href="offset-anchor"><code>offset-anchor</code></a>: for <a href="length"><code>&lt;length&gt;</code></a> the absolute value, otherwise a percentage</li><li><a href="offset-rotate"><code>offset-rotate</code></a>: as specified</li></ul></td></tr><tr class="even"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="offset-position"><code>offset-position</code></a>: a <a href="position_value#interpolation">position</a></li><li><a href="offset-path"><code>offset-path</code></a>: as &lt;angle&gt;, &lt;basic-shape&gt; or &lt;path()&gt;</li><li><a href="offset-distance"><code>offset-distance</code></a>: a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</li><li><a href="offset-anchor"><code>offset-anchor</code></a>: a <a href="position_value#interpolation">position</a></li><li><a href="offset-rotate"><code>offset-rotate</code></a>: as &lt;angle&gt;, &lt;basic-shape&gt; or &lt;path()&gt;</li></ul></td></tr><tr class="odd"><td>Creates <a href="css_positioning/understanding_z_index/the_stacking_context">stacking context</a></td><td>yes</td></tr></tbody></table>

## Formal syntax

    [ <'offset-position'>? [ <'offset-path'> [ <'offset-distance'> || <'offset-rotate'> ]? ]? ]! [ / <'offset-anchor'> ]?

## Examples

### Animating an element along a path

#### HTML

    <div id="offsetElement"></div>

#### CSS

    @keyframes move {
      from {
        offset-distance: 0%;
      }

      to {
        offset-distance: 100%;
      }
    }

    #offsetElement {
      width: 50px;
      height: 50px;
      background-color: blue;
      offset: path("M 100 100 L 300 100 L 200 300 z") auto;
      animation: move 3s linear infinite;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/motion-1/#offset-shorthand">Motion Path Module Level 1<br />
<span class="small">The definition of 'offset' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`offset`

55

46

79

79

72

71-72

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

- [`offset-anchor`](offset-anchor)
- [`offset-distance`](offset-distance)
- [`offset-path`](offset-path)
- [`offset-position`](offset-position)
- [`offset-rotate`](offset-rotate)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/offset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/offset</a>
