# grid-area

The `grid-area` CSS [shorthand property](shorthand_properties) specifies a grid item’s size and location within a [grid](https://developer.mozilla.org/en-US/docs/Glossary/Grid) by contributing a line, a span, or nothing (automatic) to its grid placement, thereby specifying the edges of its [grid area](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas).

If four `<grid-line>` values are specified, `grid-row-start` is set to the first value, `grid-column-start` is set to the second value, `grid-row-end` is set to the third value, and `grid-column-end` is set to the fourth value.

When `grid-column-end` is omitted, if `grid-column-start` is a [`<custom-ident>`](custom-ident), `grid-column-end` is set to that `<custom-ident>`; otherwise, it is set to `auto`.

When `grid-row-end` is omitted, if `grid-row-start` is a `<custom-ident>`, `grid-row-end` is set to that `<custom-ident>`; otherwise, it is set to `auto`.

When `grid-column-start` is omitted, if `grid-row-start` is a `<custom-ident>`, all four longhands are set to that value. Otherwise, it is set to `auto`.

The grid-area property can also be set to a [`<custom-ident>`](custom-ident) which acts as a name for the area, which can then be placed using [`grid-template-areas`](grid-template-areas).

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`grid-row-start`](grid-row-start)
- [`grid-column-start`](grid-column-start)
- [`grid-row-end`](grid-row-end)
- [`grid-column-end`](grid-column-end)

## Syntax

    /* Keyword values */
    grid-area: auto;
    grid-area: auto / auto;
    grid-area: auto / auto / auto;
    grid-area: auto / auto / auto / auto;

    /* <custom-ident> values */
    grid-area: some-grid-area;
    grid-area: some-grid-area / another-grid-area;

    /* <integer> && <custom-ident>? values */
    grid-area:  4 some-grid-area;
    grid-area:  4 some-grid-area / 2 another-grid-area;

    /* span && [ <integer> || <custom-ident> ] values */
    grid-area: span 3;
    grid-area: span 3 / span some-grid-area;
    grid-area: 2 span / another-grid-area span;

    /* Global values */
    grid-area: inherit;
    grid-area: initial;
    grid-area: unset;

### Values

`auto`  
Is a keyword indicating that the property contributes nothing to the grid item’s placement, indicating auto-placement or a default span of `1`.

`<custom-ident>`  
If there is a named line with the name '`<custom-ident>-start`'/'`<custom-ident>-end`', it contributes the first such line to the grid item’s placement.

**Note:** Named grid areas automatically generate implicit named lines of this form, so specifying `grid-area: foo;` will choose the start/end edge of that named grid area (unless another line named `foo-start`/`foo-end` was explicitly specified before it).

Otherwise, this is treated as if the integer `1` had been specified along with the `<custom-ident>`.

`<integer> && <custom-ident>?`  
Contributes the *n*th grid line to the grid item’s placement. If a negative integer is given, it instead counts in reverse, starting from the end edge of the explicit grid.

If a name is given as a [`<custom-ident>`](custom-ident), only lines with that name are counted. If not enough lines with that name exist, all implicit grid lines are assumed to have that name for the purpose of finding this position.

An [`<integer>`](integer) value of `0` is invalid.

`span && [ <integer> || <custom-ident> ]`  
Contributes a grid span to the grid item’s placement such that the corresponding edge of the grid item’s grid area is _n_ lines from the opposite edge.

If a name is given as a [`<custom-ident>`](custom-ident), only lines with that name are counted. If not enough lines with that name exist, all implicit grid lines on the side of the explicit grid corresponding to the search direction are assumed to have that name for the purpose of counting this span.

If the [`<integer>`](integer) is omitted, it defaults to `1`. Negative integers or 0 are invalid.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="grid-row-start"><code>grid-row-start</code></a>: <code>auto</code></li><li><a href="grid-column-start"><code>grid-column-start</code></a>: <code>auto</code></li><li><a href="grid-row-end"><code>grid-row-end</code></a>: <code>auto</code></li><li><a href="grid-column-end"><code>grid-column-end</code></a>: <code>auto</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>grid items and absolutely-positioned boxes whose containing block is a grid container</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="grid-row-start"><code>grid-row-start</code></a>: as specified</li><li><a href="grid-column-start"><code>grid-column-start</code></a>: as specified</li><li><a href="grid-row-end"><code>grid-row-end</code></a>: as specified</li><li><a href="grid-column-end"><code>grid-column-end</code></a>: as specified</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <grid-line> [ / <grid-line> ]{0,3}where
    <grid-line> = auto | <custom-ident> | [ <integer> && <custom-ident>? ] | [ span && [ <integer> || <custom-ident> ] ]

## Examples

### Setting grid areas

#### HTML

    <div id="grid">
      <div id="item1"></div>
      <div id="item2"></div>
      <div id="item3"></div>
    </div>

#### CSS

    #grid {
      display: grid;
      height: 100px;
      grid-template: repeat(4, 1fr) / 50px 100px;
    }

    #item1 {
      background-color: lime;
      grid-area: 2 / 2 / auto / span 3;
    }

    #item2 {
      background-color: yellow;
    }

    #item3 {
      background-color: blue;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid/#propdef-grid-area">CSS Grid Layout<br />
<span class="small">The definition of 'grid-area' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`grid-area`

57

16

52

No

44

10.1

57

57

52

43

10.3

6.0

## See also

- Related CSS properties: [`grid-row`](grid-row), [`grid-row-start`](grid-row-start), [`grid-row-end`](grid-row-end), [`grid-column`](grid-column), [`grid-column-start`](grid-column-start), [`grid-column-end`](grid-column-end), [`grid-template-areas`](grid-template-areas)
- Grid Layout Guide: _[Grid template areas](css_grid_layout/grid_template_areas)_
- Video tutorial: _[Grid Template Areas](https://gridbyexample.com/video/grid-template-areas/)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/grid-area" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/grid-area</a>
