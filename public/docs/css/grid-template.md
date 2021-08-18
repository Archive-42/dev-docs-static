# grid-template

The `grid-template` CSS property is a [shorthand property](shorthand_properties) for defining [grid columns](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Column), [rows](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Rows), and [areas](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas).

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`grid-template-areas`](grid-template-areas)
- [`grid-template-columns`](grid-template-columns)
- [`grid-template-rows`](grid-template-rows)

## Syntax

    /* Keyword value */
    grid-template: none;

    /* grid-template-rows / grid-template-columns values */
    grid-template: 100px 1fr / 50px 1fr;
    grid-template: auto 1fr / auto 1fr auto;
    grid-template: [linename] 100px / [columnname1] 30% [columnname2] 70%;
    grid-template: fit-content(100px) / fit-content(40%);

    /* grid-template-areas grid-template-rows / grid-template-column values */
    grid-template: "a a a"
                   "b b b";
    grid-template: "a a a" 20%
                   "b b b" auto;
    grid-template: [header-top] "a a a"     [header-bottom]
                     [main-top] "b b b" 1fr [main-bottom]
                                / auto 1fr auto;

    /* Global values */
    grid-template: inherit;
    grid-template: initial;
    grid-template: unset;

### Values

`none`  
Is a keyword that sets all three longhand properties to `none`, meaning there is no explicit grid. There are no named grid areas. Rows and columns will be implicitly generated; their size will be determined by the [`grid-auto-rows`](grid-auto-rows) and [`grid-auto-columns`](grid-auto-columns) properties.

`<'grid-template-rows'> / <'grid-template-columns'>`  
Sets [`grid-template-rows`](grid-template-rows) and [`grid-template-columns`](grid-template-columns) to the specified values, and sets [`grid-template-areas`](grid-template-areas) to `none`.

`[ <line-names>? <string> <track-size>? <line-names>? ]+ [ / <explicit-track-list> ]?`  
Sets [`grid-template-areas`](grid-template-areas) to the strings listed, [`grid-template-rows`](grid-template-rows) to the track sizes following each string (filling in `auto` for any missing sizes), and splicing in the named lines defined before/after each size, and [`grid-template-columns`](grid-template-columns) to the track listing specified after the slash (or `none`, if not specified).

Note: The [`repeat()`](<repeat()>) function isn’t allowed in these track listings, as the tracks are intended to visually line up one-to-one with the rows/columns in the “ASCII art”.

**Note:** The [`grid`](grid) shorthand accepts the same syntax, but also resets the implicit grid properties to their initial values. Use `grid` (as opposed to `grid-template`) to prevent these values from cascading in separately.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="grid-template-columns"><code>grid-template-columns</code></a>: <code>none</code></li><li><a href="grid-template-rows"><code>grid-template-rows</code></a>: <code>none</code></li><li><a href="grid-template-areas"><code>grid-template-areas</code></a>: <code>none</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>grid containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="grid-template-columns"><code>grid-template-columns</code></a>: refer to corresponding dimension of the content area</li><li><a href="grid-template-rows"><code>grid-template-rows</code></a>: refer to corresponding dimension of the content area</li></ul></td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="grid-template-columns"><code>grid-template-columns</code></a>: as specified, but with relative lengths converted into absolute lengths</li><li><a href="grid-template-rows"><code>grid-template-rows</code></a>: as specified, but with relative lengths converted into absolute lengths</li><li><a href="grid-template-areas"><code>grid-template-areas</code></a>: as specified</li></ul></td></tr><tr class="even"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | [ <'grid-template-rows'> / <'grid-template-columns'> ] | [ <line-names>? <string> <track-size>? <line-names>? ]+ [ / <explicit-track-list> ]?where
    <line-names> = '[' <custom-ident>* ']'
    <track-size> = <track-breadth> | minmax( <inflexible-breadth> , <track-breadth> ) | fit-content( [ <length> | <percentage> ] )
    <explicit-track-list> = [ <line-names>? <track-size> ]+ <line-names>?where
    <track-breadth> = <length-percentage> | <flex> | min-content | max-content | auto
    <inflexible-breadth> = <length> | <percentage> | min-content | max-content | auto
    where
    <length-percentage> = <length> | <percentage>

## Examples

### Defining a grid template

#### CSS

    #page {
      display: grid;
      width: 100%;
      height: 200px;
      grid-template: [header-left] "head head" 30px [header-right]
                     [main-left]   "nav  main" 1fr  [main-right]
                     [footer-left] "nav  foot" 30px [footer-right]
                     / 120px 1fr;
    }

    header {
      background-color: lime;
      grid-area: head;
    }

    nav {
      background-color: lightblue;
      grid-area: nav;
    }

    main {
      background-color: yellow;
      grid-area: main;
    }

    footer {
      background-color: red;
      grid-area: foot;
    }

#### HTML

    <section id="page">
      <header>Header</header>
      <nav>Navigation</nav>
      <main>Main area</main>
      <footer>Footer</footer>
    </section>

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid/#propdef-grid-template">CSS Grid Layout<br />
<span class="small">The definition of 'grid-template' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`grid-template`

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

- Related CSS properties: [`grid-template-rows`](grid-template-rows), [`grid-template-columns`](grid-template-columns), [`grid-template-areas`](grid-template-areas)
- Grid Layout Guide: _[Line-based placement with CSS Grid](css_grid_layout/line-based_placement_with_css_grid)_
- Grid Layout Guide: _[Grid template areas - Grid definition shorthands](css_grid_layout/grid_template_areas#grid_definition_shorthands)_
- Video tutorial: _[Grid Template shorthand](https://gridbyexample.com/video/grid-template-shorthand/)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template</a>
