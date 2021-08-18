# grid-auto-flow

The `grid-auto-flow` CSS property controls how the auto-placement algorithm works, specifying exactly how auto-placed items get flowed into the grid.

## Syntax

    /* Keyword values */
    grid-auto-flow: row;
    grid-auto-flow: column;
    grid-auto-flow: dense;
    grid-auto-flow: row dense;
    grid-auto-flow: column dense;

    /* Global values */
    grid-auto-flow: inherit;
    grid-auto-flow: initial;
    grid-auto-flow: unset;

This property may take one of two forms:

- a single keyword: one of `row`, `column`, or `dense`.
- two keywords: `row dense` or `column dense`.

### Values

`row`  
Items are placed by filling each row in turn, adding new rows as necessary. If neither `row` nor `column` is provided, `row` is assumed.

`column`  
Items are placed by filling each column in turn, adding new columns as necessary.

`dense`  
"dense" packing algorithm attempts to fill in holes earlier in the grid, if smaller items come up later. This may cause items to appear out-of-order, when doing so would fill in holes left by larger items.

If it is omitted, a "sparse" algorithm is used, where the placement algorithm only ever moves "forward" in the grid when placing items, never backtracking to fill holes. This ensures that all of the auto-placed items appear "in order", even if this leaves holes that could have been filled by later items.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>row</code></td></tr><tr class="even"><td>Applies to</td><td>grid containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ row | column ] || dense

## Examples

### Setting grid auto-placement

#### HTML

    <div id="grid">
      <div id="item1"></div>
      <div id="item2"></div>
      <div id="item3"></div>
      <div id="item4"></div>
      <div id="item5"></div>
    </div>
    <select id="direction">
      <option value="column">column</option>
      <option value="row">row</option>
    </select>
    <input id="dense" type="checkbox">
    <label for="dense">dense</label>

#### CSS

    #grid {
      height: 200px;
      width: 200px;
      display: grid;
      gap: 10px;
      grid-template: repeat(4, 1fr) / repeat(2, 1fr);
      grid-auto-flow: column;  /* or 'row', 'row dense', 'column dense' */
    }

    #item1 {
      background-color: lime;
      grid-row-start: 3;
    }

    #item2 {
      background-color: yellow;
    }

    #item3 {
      background-color: blue;
    }

    #item4 {
      grid-column-start: 2;
      background-color: red;
    }

    #item5 {
      background-color: aqua;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid/#propdef-grid-auto-flow">CSS Grid Layout<br />
<span class="small">The definition of 'grid-auto-flow' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`grid-auto-flow`

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

- Related CSS properties: [`grid-auto-rows`](grid-auto-rows), [`grid-auto-columns`](grid-auto-columns), [`grid`](grid)
- Grid Layout Guide: _[Auto-placement in grid layout](css_grid_layout/auto-placement_in_css_grid_layout)_
- Video tutorial: _[Introducing Grid auto-placement and order](https://gridbyexample.com/video/series-auto-placement-order/)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-flow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-flow</a>
