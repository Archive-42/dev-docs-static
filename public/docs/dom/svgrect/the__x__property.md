The 'X' property
================

The [x](https://svgwg.org/svg2-draft/geometry.html#XProperty) property describes the horizontal coordinate of the position of the element.

Usage context
-------------

<table><tbody><tr class="odd"><td>Name</td><td>x</td></tr><tr class="even"><td>Value</td><td><a href="https://www.w3.org/TR/css3-values/#lengths">&lt;length&gt;</a> | <a href="https://www.w3.org/TR/css3-values/#percentages">&lt;percentage&gt;</a></td></tr><tr class="odd"><td>Initial</td><td>0</td></tr><tr class="even"><td>Applies to</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/mask"><code>&lt;mask&gt;</code></a> , ‘<a href="https://svgwg.org/svg2-draft/struct.html#SVGElement">svg</a>’, ‘<a href="https://svgwg.org/svg2-draft/shapes.html#RectElement">rect</a>’, ‘<a href="https://svgwg.org/svg2-draft/embedded.html#ImageElement">image</a>’, ‘<a href="https://svgwg.org/svg2-draft/embedded.html#ForeignObjectElement">foreignObject</a>’</td></tr><tr class="odd"><td>Inherited</td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the size of the current viewport (see <a href="https://svgwg.org/svg2-draft/coords.html#Units">Units</a>)</td></tr><tr class="odd"><td>Media</td><td>visual</td></tr><tr class="even"><td>Computed value</td><td>absolute length or percentage</td></tr><tr class="odd"><td>Animatable</td><td>yes</td></tr></tbody></table>

Simple usage
------------

A &lt;coordinate&gt; is a length in the user coordinate system that is the given distance from the origin of the user coordinate system along the relevant axis (the x-axis for X coordinates, the y-axis for Y coordinates). Its syntax is the same as that for [&lt;length&gt;](https://www.w3.org/TR/SVG11/types.html#DataTypeLength)

    // Rect draws a rectangle with upper left-hand corner at x,y, with width w, and height h, with optional style
    // Standard Reference: http://www.w3.org/TR/SVG11/shapes.html#RectElement

         func (svg *SVG) Rect(x float64, y float64, w float64, h float64, s ...string) {
                 svg.printf(`<rect %s %s`, dim(x, y, w, h, svg.Decimals), endstyle(s, emptyclose))
    }

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGRect/The__X__property" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGRect/The__X__property</a>
