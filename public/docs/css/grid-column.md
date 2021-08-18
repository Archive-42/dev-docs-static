# grid-column

The `grid-column` CSS [shorthand property](shorthand_properties) specifies a grid item's size and location within a [grid column](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Column) by contributing a line, a span, or nothing (automatic) to its grid placement, thereby specifying the inline-start and inline-end edge of its [grid area](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas).

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`grid-column-end`](grid-column-end)
- [`grid-column-start`](grid-column-start)

## Syntax

This property is specified as one or two `<grid-line>` values.

If two `<grid-line>` values are given they are separated by "/". The `grid-column-start` longhand is set to the value before the slash, and the `grid-column-end` longhand is set to the value after the slash.

Each `<grid-line>` value can be specified as:

- either the `auto` keyword
- or a `<custom-ident>` value
- or an `<integer>` value
- or both `<custom-ident>` and `<integer>`, separated by a space
- or the keyword `span` together with either a `<custom-ident>` or an `<integer>` or both.

### Values

`auto`  
Is a keyword indicating that the property contributes nothing to the grid item’s placement, indicating auto-placement, an automatic span, or a default span of `1`.

`<custom-ident>`  
If there is a named line with the name '&lt;custom-ident&gt;-start'/'&lt;custom-ident&gt;-end', it contributes the first such line to the grid item’s placement.

**Note:** Named grid areas automatically generate implicit named lines of this form, so specifying `grid-column: foo;` will choose the start/end edge of that named grid area (unless another line named `foo-start`/`foo-end` was explicitly specified before it).

Otherwise, this is treated as if the integer `1` had been specified along with the `<custom-ident>`.

`<integer> && <custom-ident>?`  
Contributes the nth grid line to the grid item’s placement. If a negative integer is given, it instead counts in reverse, starting from the end edge of the explicit grid.

If a name is given as a &lt;custom-ident&gt;, only lines with that name are counted. If not enough lines with that name exist, all implicit grid lines are assumed to have that name for the purpose of finding this position.

An [`<integer>`](integer) value of `0` is invalid.

`span && [ <integer> || <custom-ident> ]`  
Contributes a grid span to the grid item’s placement such that the corresponding edge of the grid item’s grid area is n lines from the opposite edge.

If a name is given as a &lt;custom-ident&gt;, only lines with that name are counted. If not enough lines with that name exist, all implicit grid lines on the side of the explicit grid corresponding to the search direction are assumed to have that name for the purpose of counting this span.

If the &lt;integer&gt; is omitted, it defaults to `1`. Negative integers or 0 are invalid.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="grid-column-start"><code>grid-column-start</code></a>: <code>auto</code></li><li><a href="grid-column-end"><code>grid-column-end</code></a>: <code>auto</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>grid items and absolutely-positioned boxes whose containing block is a grid container</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="grid-column-start"><code>grid-column-start</code></a>: as specified</li><li><a href="grid-column-end"><code>grid-column-end</code></a>: as specified</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <grid-line> [ / <grid-line> ]?where
    <grid-line> = auto | <custom-ident> | [ <integer> && <custom-ident>? ] | [ span && [ <integer> || <custom-ident> ] ]

## Examples

### Setting grid column size and location

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
      grid-template-columns: repeat(6, 1fr);
      grid-template-rows: 100px;
    }

    #item1 {
      background-color: lime;
    }

    #item2 {
      background-color: yellow;
      grid-column: 2 / 4;
    }

    #item3 {
      background-color: blue;
      grid-column: span 2 / 7;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid/#propdef-grid-column">CSS Grid Layout<br />
<span class="small">The definition of 'grid-column' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`grid-column`

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

- Related CSS properties: [`grid-row`](grid-row), [`grid-row-start`](grid-row-start), [`grid-row-end`](grid-row-end), [`grid-column-start`](grid-column-start), [`grid-column-end`](grid-column-end)
- Grid Layout Guide: _[Line-based placement with CSS Grid](css_grid_layout/line-based_placement_with_css_grid)_
- Video tutorial: _[Line-based placement](https://gridbyexample.com/video/series-line-based-placement/)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column</a>
