# grid-template-areas

The `grid-template-areas` CSS property specifies named [grid areas](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas), establishing the cells in the grid and assigning them names.

Those areas are not associated with any particular grid item, but can be referenced from the grid-placement properties [`grid-row-start`](grid-row-start), [`grid-row-end`](grid-row-end), [`grid-column-start`](grid-column-start), [`grid-column-end`](grid-column-end), and their shorthands [`grid-row`](grid-row), [`grid-column`](grid-column), and [`grid-area`](grid-area).

## Syntax

    /* Keyword value */
    grid-template-areas: none;

    /* <string> values */
    grid-template-areas: "a b";
    grid-template-areas: "a b b"
                         "a c d";

    /* Global values */
    grid-template-areas: inherit;
    grid-template-areas: initial;
    grid-template-areas: unset;

### Values

`none`  
The grid container doesn’t define any named grid areas.

`<string>`+  
A row is created for every separate string listed, and a column is created for each cell in the string. Multiple named cell tokens within and between rows create a single named grid area that spans the corresponding grid cells. Unless those cells form a rectangle, the declaration is invalid.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>grid containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | <string>+

## Examples

### Specifying named grid areas

#### HTML

    <section id="page">
      <header>Header</header>
      <nav>Navigation</nav>
      <main>Main area</main>
      <footer>Footer</footer>
    </section>

#### CSS

    #page {
      display: grid;
      width: 100%;
      height: 250px;
      grid-template-areas: "head head"
                           "nav  main"
                           "nav  foot";
      grid-template-rows: 50px 1fr 30px;
      grid-template-columns: 150px 1fr;
    }

    #page > header {
      grid-area: head;
      background-color: #8ca0ff;
    }

    #page > nav {
      grid-area: nav;
      background-color: #ffa08c;
    }

    #page > main {
      grid-area: main;
      background-color: #ffff64;
    }

    #page > footer {
      grid-area: foot;
      background-color: #8cffa0;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid/#propdef-grid-template-areas">CSS Grid Layout<br />
<span class="small">The definition of 'grid-template-areas' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`grid-template-areas`

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

- Related CSS properties: [`grid-template-rows`](grid-template-rows), [`grid-template-columns`](grid-template-columns), [`grid-template`](grid-template)
- Grid Layout Guide: _[Grid template areas](css_grid_layout/grid_template_areas)_
- Video tutorial: _[Grid Template Areas](https://gridbyexample.com/video/grid-template-areas/)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas</a>
