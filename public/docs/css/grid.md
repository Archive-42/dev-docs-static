# grid

The `grid` CSS property is a [shorthand property](shorthand_properties) that sets all of the explicit and implicit grid properties in a single declaration.

Using `grid` you specify one axis using [`grid-template-rows`](grid-template-rows) or [`grid-template-columns`](grid-template-columns), you then specify how content should auto-repeat in the other axis using the implicit grid properties: [`grid-auto-rows`](grid-auto-rows), [`grid-auto-columns`](grid-auto-columns), and [`grid-auto-flow`](grid-auto-flow).

**Note**

The sub-properties you don’t specify are set to their initial value, as normal for shorthands. Also, the gutter properties are NOT reset by this shorthand.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`grid-auto-columns`](grid-auto-columns)
- [`grid-auto-flow`](grid-auto-flow)
- [`grid-auto-rows`](grid-auto-rows)
- [`grid-template-areas`](grid-template-areas)
- [`grid-template-columns`](grid-template-columns)
- [`grid-template-rows`](grid-template-rows)

## Syntax

    /* <'grid-template'> values */
    grid: none;
    grid: "a" 100px "b" 1fr;
    grid: [linename1] "a" 100px [linename2];
    grid: "a" 200px "b" min-content;
    grid: "a" minmax(100px, max-content) "b" 20%;
    grid: 100px / 200px;
    grid: minmax(400px, min-content) / repeat(auto-fill, 50px);

    /* <'grid-template-rows'> /
       [ auto-flow && dense? ] <'grid-auto-columns'>? values */
    grid: 200px / auto-flow;
    grid: 30% / auto-flow dense;
    grid: repeat(3, [line1 line2 line3] 200px) / auto-flow 300px;
    grid: [line1] minmax(20em, max-content) / auto-flow dense 40%;

    /* [ auto-flow && dense? ] <'grid-auto-rows'>? /
       <'grid-template-columns'> values */
    grid: auto-flow / 200px;
    grid: auto-flow dense / 30%;
    grid: auto-flow 300px / repeat(3, [line1 line2 line3] 200px);
    grid: auto-flow dense 40% / [line1] minmax(20em, max-content);

    /* Global values */
    grid: inherit;
    grid: initial;
    grid: unset;

### Values

`<'grid-template'>`  
Defines the [`grid-template`](grid-template) including [`grid-template-columns`](grid-template-columns), [`grid-template-rows`](grid-template-rows) and [`grid-template-areas`](grid-template-areas).

`<'grid-template-rows'> / [ auto-flow && dense? ] <'grid-auto-columns'>?`  
Sets up an auto-flow by setting the row tracks explicitly via the [`grid-template-rows`](grid-template-rows) property (and the [`grid-template-columns`](grid-template-columns) property to `none`) and specifying how to auto-repeat the column tracks via [`grid-auto-columns`](grid-auto-columns) (and setting [`grid-auto-rows`](grid-auto-rows) to `auto`). [`grid-auto-flow`](grid-auto-flow) is also set to `column` accordingly, with `dense` if it’s specified.

All other `grid` sub-properties are reset to their initial values.

`[ auto-flow && dense? ] <'grid-auto-rows'>? / <'grid-template-columns'>`  
Sets up an auto-flow by setting the column tracks explicitly via the [`grid-template-columns`](grid-template-columns) property (and the [`grid-template-rows`](grid-template-rows) property to `none`) and specifying how to auto-repeat the row tracks via [`grid-auto-rows`](grid-auto-rows) (and setting [`grid-auto-columns`](grid-auto-columns) to `auto`). [`grid-auto-flow`](grid-auto-flow) is also set to `row` accordingly, with `dense` if it’s specified.

All other `grid` sub-properties are reset to their initial values.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="grid-template-rows"><code>grid-template-rows</code></a>: <code>none</code></li><li><a href="grid-template-columns"><code>grid-template-columns</code></a>: <code>none</code></li><li><a href="grid-template-areas"><code>grid-template-areas</code></a>: <code>none</code></li><li><a href="grid-auto-rows"><code>grid-auto-rows</code></a>: <code>auto</code></li><li><a href="grid-auto-columns"><code>grid-auto-columns</code></a>: <code>auto</code></li><li><a href="grid-auto-flow"><code>grid-auto-flow</code></a>: <code>row</code></li><li><a href="column-gap"><code>grid-column-gap</code></a>: <code>0</code></li><li><a href="row-gap"><code>grid-row-gap</code></a>: <code>0</code></li><li><a href="column-gap"><code>column-gap</code></a>: <code>normal</code></li><li><a href="row-gap"><code>row-gap</code></a>: <code>normal</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>grid containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="grid-template-rows"><code>grid-template-rows</code></a>: refer to corresponding dimension of the content area</li><li><a href="grid-template-columns"><code>grid-template-columns</code></a>: refer to corresponding dimension of the content area</li><li><a href="grid-auto-rows"><code>grid-auto-rows</code></a>: refer to corresponding dimension of the content area</li><li><a href="grid-auto-columns"><code>grid-auto-columns</code></a>: refer to corresponding dimension of the content area</li></ul></td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="grid-template-rows"><code>grid-template-rows</code></a>: as specified, but with relative lengths converted into absolute lengths</li><li><a href="grid-template-columns"><code>grid-template-columns</code></a>: as specified, but with relative lengths converted into absolute lengths</li><li><a href="grid-template-areas"><code>grid-template-areas</code></a>: as specified</li><li><a href="grid-auto-rows"><code>grid-auto-rows</code></a>: the percentage as specified or the absolute length</li><li><a href="grid-auto-columns"><code>grid-auto-columns</code></a>: the percentage as specified or the absolute length</li><li><a href="grid-auto-flow"><code>grid-auto-flow</code></a>: as specified</li><li><a href="column-gap"><code>grid-column-gap</code></a>: the percentage as specified or the absolute length</li><li><a href="row-gap"><code>grid-row-gap</code></a>: the percentage as specified or the absolute length</li><li><a href="column-gap"><code>column-gap</code></a>: as specified, with &lt;length&gt;s made absolute, and normal computing to zero except on multi-column elements</li><li><a href="row-gap"><code>row-gap</code></a>: as specified, with &lt;length&gt;s made absolute, and normal computing to zero except on multi-column elements</li></ul></td></tr><tr class="even"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <'grid-template'> | <'grid-template-rows'> / [ auto-flow && dense? ] <'grid-auto-columns'>? | [ auto-flow && dense? ] <'grid-auto-rows'>? / <'grid-template-columns'>

## Examples

### Creating a grid layout

#### HTML

    <div id="container">
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>

#### CSS

    #container {
      display: grid;
      grid: repeat(2, 60px) / auto-flow 80px;
    }

    #container > div {
      background-color: #8ca0ff;
      width: 50px;
      height: 50px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid/#propdef-grid">CSS Grid Layout<br />
<span class="small">The definition of 'grid' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`grid`

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

This was added early so is out of sync with the equivalent Chromium version.

## See also

- Related CSS properties: [`grid-template`](grid-template), [`grid-template-rows`](grid-template-rows), [`grid-template-columns`](grid-template-columns), [`grid-template-areas`](grid-template-areas), [`grid-auto-columns`](grid-auto-columns), [`grid-auto-rows`](grid-auto-rows), [`grid-auto-flow`](grid-auto-flow)
- Grid Layout Guide: _[Line-based placement with CSS Grid](css_grid_layout/line-based_placement_with_css_grid)_
- Grid Layout Guide: _[Grid template areas - Grid definition shorthands](css_grid_layout/grid_template_areas#grid_definition_shorthands)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/grid" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/grid</a>
