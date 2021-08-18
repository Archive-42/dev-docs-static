# clip-path

The `clip-path` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property creates a clipping region that sets what part of an element should be shown. Parts that are inside the region are shown, while those outside are hidden.

## Syntax

    /* Keyword values */
    clip-path: none;

    /* <clip-source> values */
    clip-path: url(resources.svg#c1);

    /* <geometry-box> values */
    clip-path: margin-box;
    clip-path: border-box;
    clip-path: padding-box;
    clip-path: content-box;
    clip-path: fill-box;
    clip-path: stroke-box;
    clip-path: view-box;

    /* <basic-shape> values */
    clip-path: inset(100px 50px);
    clip-path: circle(50px at 0 100px);
    clip-path: ellipse(50px 60px at 0 10% 20%);
    clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
    clip-path: path('M0.5,1 C0.5,1,0,0.7,0,0.3 A0.25,0.25,1,1,1,0.5,0.3 A0.25,0.25,1,1,1,1,0.3 C1,0.7,0.5,1,0.5,1 Z');

    /* Box and shape values combined */
    clip-path: padding-box circle(50px at 0 100px);

    /* Global values */
    clip-path: inherit;
    clip-path: initial;
    clip-path: unset;

The `clip-path` property is specified as one or a combination of the values listed below.

### Values

`<clip-source>`  
A [`<url>()`](<url()>) referencing an [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG) [`<clipPath>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/clipPath) element.

[`<basic-shape>`](basic-shape)  
A shape whose size and position is defined by the `<geometry-box>` value. If no geometry box is specified, the `border-box` will be used as the reference box.

`<geometry-box>`  
If specified in combination with a `<basic-shape>`, this value defines the reference box for the basic shape. If specified by itself, it causes the edges of the specified box, including any corner shaping (such as a [`border-radius`](border-radius)), to be the clipping path. The geometry box can be one of the following values:

`margin-box`  
Uses the [margin box](css_shapes/from_box_values#margin-box) as the reference box.

`border-box`  
Uses the [border box](css_shapes/from_box_values#border-box) as the reference box.

`padding-box`  
Uses the [padding box](css_shapes/from_box_values#padding-box) as the reference box.

`content-box`  
Uses the [content box](css_shapes/from_box_values#content-box) as the reference box.

`fill-box`  
Uses the object bounding box as the reference box.

`stroke-box`  
Uses the stroke bounding box as the reference box.

`view-box`  
Uses the nearest SVG viewport as the reference box. If a `viewBox` attribute is specified for the element creating the SVG viewport, the reference box is positioned at the origin of the coordinate system established by the `viewBox` attribute and the dimension of the size of the reference box is set to the width and height values of the `viewBox` attribute.

`none`  
No clipping path is created.

**Note**: A computed value other than `none` results in the creation of a new [stacking context](css_positioning/understanding_z_index/the_stacking_context) the same way that CSS [`opacity`](opacity) does for values other than `1`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to reference box when specified, otherwise border-box</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified, but with <a href="url()"><code>url()</code></a> values made absolute</td></tr><tr class="even"><td>Animation type</td><td>yes, as specified for <a href="basic-shape"><code>&lt;basic-shape&gt;</code></a>, otherwise no</td></tr></tbody></table>

## Formal syntax

    <clip-source> | [ <basic-shape> || <geometry-box> ] | nonewhere
    <clip-source> = <url>
    <basic-shape> = <inset()> | <circle()> | <ellipse()> | <polygon()> | <path()>
    <geometry-box> = <shape-box> | fill-box | stroke-box | view-boxwhere
    <inset()> = inset( <length-percentage>{1,4} [ round <'border-radius'> ]? )
    <circle()> = circle( [ <shape-radius> ]? [ at <position> ]? )
    <ellipse()> = ellipse( [ <shape-radius>{2} ]? [ at <position> ]? )
    <polygon()> = polygon( <fill-rule>? , [ <length-percentage> <length-percentage> ]# )
    <path()> = path( [ <fill-rule>, ]? <string> )
    <shape-box> = <box> | margin-boxwhere
    <length-percentage> = <length> | <percentage>
    <shape-radius> = <length-percentage> | closest-side | farthest-side
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]
    <fill-rule> = nonzero | evenodd
    <box> = border-box | padding-box | content-box

## Examples

### Comparison of HTML and SVG

### Complete example

#### HTML

    <img id="clipped" src="https://mdn.mozillademos.org/files/12668/MDN.svg"
        alt="MDN logo">
    <svg height="0" width="0">
      <defs>
        <clipPath id="cross">
          <rect y="110" x="137" width="90" height="90"/>
          <rect x="0" y="110" width="90" height="90"/>
          <rect x="137" y="0" width="90" height="90"/>
          <rect x="0" y="0" width="90" height="90"/>
        </clipPath>
      </defs>
    </svg>

    <select id="clipPath">
      <option value="none">none</option>
      <option value="circle(100px at 110px 100px)">circle</option>
      <option value="url(#cross)" selected>cross</option>
      <option value="inset(20px round 20px)">inset</option>
      <option value="path('M 0 200 L 0,110 A 110,90 0,0,1 240,100 L 200 340 z')">path</option>
    </select>

#### CSS

    #clipped {
      margin-bottom: 20px;
      clip-path: url(#cross);
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#the-clip-path">CSS Masking Module Level 1<br />
<span class="small">The definition of 'clip-path' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Extends its application to HTML elements. The <code>clip-path</code> property replaces the deprecated <a href="clip"><code>clip</code></a> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/masking.html#ClipPathProperty">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'clip-path' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition (applies to SVG elements only).</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-shapes-2/#supported-basic-shapes">CSS Shapes Module Level 2<br />
<span class="small">The definition of 'path' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Defines <code>path()</code>.</td></tr></tbody></table>

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

`clip-path`

55

23

12

Edge only supports clip paths defined by `url()`.

3.5

10

Internet Explorer only supports clip paths defined by `url()`.

42

15

9.1

6.1

55

≤37

55

25

4

42

14

9.3

6.1

6.0

1.5

`animations`

55

79

49

No

42

No

55

55

49

42

No

6.0

`basic_shape`

23

79

54

No

15

6.1

4.4

25

54

14

6.1

1.5

`fill_and_stroke_box`

No

No

51

This value was supported before Firefox 51, but as an alias to `border-box`.

No

No

No

No

No

51

This value was supported before Firefox 51, but as an alias to `border-box`.

No

No

No

`html`

23

79

3.5

No

15

6.1

4.4

25

4

14

6.1

1.5

`path`

88

88

71

63

No

No

13.1

10

88

88

63

No

13

10

No

`svg`

23

12

52

10

15

6.1

4.4

25

52

14

6.1

1.5

## See also

- [Shapes in clipping and masking – and how to use them](https://hacks.mozilla.org/2017/06/css-shapes-clipping-and-masking/)
- CSS properties: [`mask`](mask), [`filter`](filter)
- [Applying SVG effects to HTML content](https://developer.mozilla.org/en-US/docs/Web/SVG/Applying_SVG_effects_to_HTML_content)
- SVG attributes:
  - `clip-path`
  - `clip-rule`

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path</a>
