# CSS Grid Layout

**CSS Grid Layout** excels at dividing a page into major regions or defining the relationship in terms of size, position, and layer, between parts of a control built from HTML primitives.

Like tables, grid layout enables an author to align elements into columns and rows. However, many more layouts are either possible or easier with CSS grid than they were with tables. For example, a grid container's child elements could position themselves so they actually overlap and layer, similar to CSS positioned elements.

## Basic example

The example below shows a three-column track grid with new rows created at a minimum of 100 pixels and a maximum of auto. Items have been placed onto the grid using line-based placement.

### HTML

    <div class="wrapper">
      <div class="one">One</div>
      <div class="two">Two</div>
      <div class="three">Three</div>
      <div class="four">Four</div>
      <div class="five">Five</div>
      <div class="six">Six</div>
    </div>

### CSS

    .wrapper {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
      grid-auto-rows: minmax(100px, auto);
    }
    .one {
      grid-column: 1 / 3;
      grid-row: 1;
    }
    .two {
      grid-column: 2 / 4;
      grid-row: 1 / 3;
    }
    .three {
      grid-column: 1;
      grid-row: 2 / 5;
    }
    .four {
      grid-column: 3;
      grid-row: 3;
    }
    .five {
      grid-column: 2;
      grid-row: 4;
    }
    .six {
      grid-column: 3;
      grid-row: 4;
    }

## Reference

### CSS properties

- [`grid-template-columns`](grid-template-columns)
- [`grid-template-rows`](grid-template-rows)
- [`grid-template-areas`](grid-template-areas)
- [`grid-template`](grid-template)
- [`grid-auto-columns`](grid-auto-columns)
- [`grid-auto-rows`](grid-auto-rows)
- [`grid-auto-flow`](grid-auto-flow)
- [`grid`](grid)
- [`grid-row-start`](grid-row-start)
- [`grid-column-start`](grid-column-start)
- [`grid-row-end`](grid-row-end)
- [`grid-column-end`](grid-column-end)
- [`grid-row`](grid-row)
- [`grid-column`](grid-column)
- [`grid-area`](grid-area)
- [`row-gap`](row-gap)
- [`column-gap`](column-gap)
- [`gap`](gap)
- [`masonry-auto-flow`](masonry-auto-flow)<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`align-tracks`](align-tracks)<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`justify-tracks`](justify-tracks)<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

### CSS functions

- [`repeat()`](<repeat()>)
- [`minmax()`](<minmax()>)
- [`fit-content()`](<fit-content()>)

### CSS data types

- [`<flex>`](flex_value)

### Glossary entries

- [Grid](https://developer.mozilla.org/en-US/docs/Glossary/Grid)
- [Grid Lines](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Lines)
- [Grid Tracks](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Tracks)
- [Grid Cell](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Cell)
- [Grid Area](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas)
- [Gutters](https://developer.mozilla.org/en-US/docs/Glossary/Gutters)
- [Grid Axis](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Axis)
- [Grid row](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Rows)
- [Grid column](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Column)

## Guides

- [Basic concepts of Grid Layout](css_grid_layout/basic_concepts_of_grid_layout)
- [Relationship of Grid Layout to other layout methods](css_grid_layout/relationship_of_grid_layout)
- [Layout using line-based placement](css_grid_layout/line-based_placement_with_css_grid)
- [Grid template areas](css_grid_layout/grid_template_areas)
- [Layout using named grid lines](css_grid_layout/layout_using_named_grid_lines)
- [Auto-placement in CSS Grid Layout](css_grid_layout/auto-placement_in_css_grid_layout)
- [Box alignment in CSS Grid Layout](css_grid_layout/box_alignment_in_css_grid_layout)
- [CSS Grid, Logical Values and Writing Modes](css_grid_layout/css_grid_logical_values_and_writing_modes)
- [CSS Grid Layout and accessibility](css_grid_layout/css_grid_layout_and_accessibility)
- [CSS Grid and progressive enhancement](css_grid_layout/css_grid_and_progressive_enhancement)
- [Realising common layouts using CSS Grid](css_grid_layout/realizing_common_layouts_using_css_grid_layout)
- [Subgrid](css_grid_layout/subgrid)
- [Masonry Layout](css_grid_layout/masonry_layout)<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

## External resources

- [CSS Grid and IE11](https://tomrothe.de/posts/css_grid_and_ie11.html) ([polyfill](https://github.com/motine/css_grid_annotator))
- [Examples from Jen Simmons](https://labs.jensimmons.com/)
- [Grid by Example - a collection of usage examples and video tutorials](https://gridbyexample.com/)
- [Codrops Grid Reference](https://tympanus.net/codrops/css_reference/grid/)
- [Firefox DevTools CSS Grid Inspector](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Examine_grid_layouts)
- [CSS Grid Playground](https://mozilladevelopers.github.io/playground/)
- [Grid Garden](https://cssgridgarden.com) - A game for learning CSS grid

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid-3/">CSS Grid Layout Module Level 3</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds <a href="css_grid_layout/masonry_layout">masonry</a>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-grid-2/">CSS Grid Layout Module Level 2</a></td><td><span class="spec-wd">Working Draft</span></td><td>Added <a href="css_grid_layout/basic_concepts_of_grid_layout#subgrid">subgrids</a>.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid/">CSS Grid Layout</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout</a>
