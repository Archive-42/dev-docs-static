# path()

The `path()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) accepts an SVG path string, and is used in CSS Shapes and CSS Motion Path to enable a shape to be drawn.

## Syntax

    path( [[<'fill-rule'>,]?<string>)

### Parameters

`<'fill-rule'>`  
The filling rule for the interior of the path. Possible values are nonzero or evenodd. The default value is nonzero. See [fill-rule](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/fill-rule) for more details.

&lt;string&gt;  
The string is an [SVG path data string](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/path).

## Examples

### Examples of correct values for path()

    path("M 10 80 C 40 10, 65 10, 95 80 S 150 150, 180 80");
    path(evenodd,"M 10 80 C 40 10, 65 10, 95 80 S 150 150, 180 80");

### Use as the value of offset-path

The `path()` function is used to create a path for the item to travel round. Changing any of the values will cause the path to not neatly run round the circle.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-shapes/#funcdef-path">CSS Shapes Module Level 1<br />
<span class="small">The definition of 'path()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td></tr></tbody></table>

## See also

- [`<shape-outside>`](shape-outside)
- [CSS Shapes](css_shapes)
- [Overview of CSS Shapes](css_shapes/overview_of_css_shapes)
- [SVG Path Syntax Illustrated Guide](https://css-tricks.com/svg-path-syntax-illustrated-guide/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/path()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/path()</a>
