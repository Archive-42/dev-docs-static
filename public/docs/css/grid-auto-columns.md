# grid-auto-columns

The `grid-auto-columns` CSS property specifies the size of an implicitly-created grid column [track](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Tracks) or pattern of tracks.

If a grid item is positioned into a column that is not explicitly sized by [`grid-template-columns`](grid-template-columns), implicit [grid](https://developer.mozilla.org/en-US/docs/Glossary/Grid) tracks are created to hold it. This can happen either by explicitly positioning into a column that is out of range, or by the auto-placement algorithm creating additional columns.

## Syntax

    /* Keyword values */
    grid-auto-columns: min-content;
    grid-auto-columns: max-content;
    grid-auto-columns: auto;

    /* <length> values */
    grid-auto-columns: 100px;
    grid-auto-columns: 20cm;
    grid-auto-columns: 50vmax;

    /* <percentage> values */
    grid-auto-columns: 10%;
    grid-auto-columns: 33.3%;

    /* <flex> values */
    grid-auto-columns: 0.5fr;
    grid-auto-columns: 3fr;

    /* minmax() values */
    grid-auto-columns: minmax(100px, auto);
    grid-auto-columns: minmax(max-content, 2fr);
    grid-auto-columns: minmax(20%, 80vmax);

    /* fit-content() values */
    grid-auto-columns: fit-content(400px);
    grid-auto-columns: fit-content(5cm);
    grid-auto-columns: fit-content(20%);

    /* multiple track-size values */
    grid-auto-columns: min-content max-content auto;
    grid-auto-columns: 100px 150px 390px;
    grid-auto-columns: 10% 33.3%;
    grid-auto-columns: 0.5fr 3fr 1fr;
    grid-auto-columns: minmax(100px, auto) minmax(max-content, 2fr) minmax(20%, 80vmax);
    grid-auto-columns: 100px minmax(100px, auto) 10% 0.5fr fit-content(400px);

    /* Global values */
    grid-auto-columns: inherit;
    grid-auto-columns: initial;
    grid-auto-columns: unset;

### Values

[`<length>`](length)  
Is a non-negative length.

[`<percentage>`](percentage)  
Is a non-negative [`<percentage>`](percentage) value relative to the block size of the grid container. If the block size of the grid container is indefinite, the percentage value is treated like `auto`.

[`<flex>`](flex_value)  
Is a non-negative dimension with the unit `fr` specifying the track’s flex factor. Each `<flex>`-sized track takes a share of the remaining space in proportion to its flex factor.

When appearing outside a `minmax()` notation, it implies an automatic minimum (i.e. `minmax(auto, <flex>)`).

[`max-content`](max-content)  
Is a keyword representing the largest maximal content contribution of the grid items occupying the grid track.

[`min-content`](min-content)  
Is a keyword representing the largest minimal content contribution of the grid items occupying the grid track.

[`minmax(min, max)`](<minmax()>)  
Is a functional notation that defines a size range greater than or equal to _min_ and less than or equal to _max_. If _max_ is smaller than _min_, then _max_ is ignored and the function is treated as _min_. As a maximum, a `<flex>` value sets the track’s flex factor. As a minimum, it is treated as zero (or minimal content, if the grid container is sized under a minimal content constraint).

[`fit-content( [ <length> | <percentage> ] )`](<fit-content()>)  
Represents the formula `min(max-content, max(auto, argument))`, which is calculated similar to `auto` (i.e. `minmax(auto, max-content)`), except that the track size is clamped at argument if it is greater than the `auto` minimum.

`auto`  
Is a keyword that is identical to maximal content if it's a maximum. As a minimum it represents the largest minimum size (as specified by [`min-width`](min-width)/[`min-height`](min-height)) of the grid items occupying the grid track.

**Note**
`auto` track sizes (and only `auto` track sizes) can be stretched by the [`align-content`](align-content) and [`justify-content`](justify-content) properties.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>grid containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to corresponding dimension of the content area</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>the percentage as specified or the absolute length</td></tr><tr class="even"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <track-size>+where
    <track-size> = <track-breadth> | minmax( <inflexible-breadth> , <track-breadth> ) | fit-content( [ <length> | <percentage> ] )where
    <track-breadth> = <length-percentage> | <flex> | min-content | max-content | auto
    <inflexible-breadth> = <length> | <percentage> | min-content | max-content | autowhere
    <length-percentage> = <length> | <percentage>

## Examples

### Setting grid column size

#### HTML

    <div id="grid">
      <div id="item1"></div>
      <div id="item2"></div>
      <div id="item3"></div>
    </div>

#### CSS

    #grid {
      height: 100px;
      display: grid;
      grid-template-areas: "a a";
      gap: 10px;
      grid-auto-columns: 200px;
    }

    #grid > div {
      background-color: lime;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid/#propdef-grid-auto-columns">CSS Grid Layout<br />
<span class="small">The definition of 'grid-auto-columns' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`grid-auto-columns`

57

16

12-79

70

52-70

Does not accept multiple track-size values. See [bug 1339672](https://bugzil.la/1339672).

10

44

10.1

57

57

79

52-79

Does not accept multiple track-size values. See [bug 1339672](https://bugzil.la/1339672).

43

10.3

6.0

## See also

- Related CSS properties: [`grid-auto-rows`](grid-auto-rows), [`grid-auto-flow`](grid-auto-flow), [`grid`](grid)
- Grid Layout Guide: _[Auto-placement in grid layout - sizing rows in the implicit grid](css_grid_layout/auto-placement_in_css_grid_layout#sizing_rows_in_the_implicit_grid)_
- Video tutorial: _[Introducing Grid auto-placement and order](https://gridbyexample.com/video/series-auto-placement-order/)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-columns" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-columns</a>
