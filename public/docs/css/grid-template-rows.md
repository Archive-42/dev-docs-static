# grid-template-rows

The `grid-template-rows` CSS property defines the line names and track sizing functions of the [grid rows](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Rows).

## Syntax

    /* Keyword value */
    grid-template-rows: none;

    /* <track-list> values */
    grid-template-rows: 100px 1fr;
    grid-template-rows: [linename] 100px;
    grid-template-rows: [linename1] 100px [linename2 linename3];
    grid-template-rows: minmax(100px, 1fr);
    grid-template-rows: fit-content(40%);
    grid-template-rows: repeat(3, 200px);
    grid-template-rows: subgrid;
    grid-template-rows: masonry;

    /* <auto-track-list> values */
    grid-template-rows: 200px repeat(auto-fill, 100px) 300px;
    grid-template-rows: minmax(100px, max-content)
                           repeat(auto-fill, 200px) 20%;
    grid-template-rows: [linename1] 100px [linename2]
                           repeat(auto-fit, [linename3 linename4] 300px)
                           100px;
    grid-template-rows: [linename1 linename2] 100px
                           repeat(auto-fit, [linename1] 300px) [linename3];

    /* Global values */
    grid-template-rows: inherit;
    grid-template-rows: initial;
    grid-template-rows: unset;

This property may be specified as:

- either the keyword value `none`
- or a `<track-list>` value
- or an `<auto-track-list>` value.

### Values

`none`  
Is a keyword meaning that there is no explicit grid. Any rows will be implicitly generated and their size will be determined by the [`grid-auto-rows`](grid-auto-rows) property.

`[linename]`  
A `<custom-ident>` specifying a name for the line in that location. The ident may be any valid string other then the reserved words `span` and `auto`. Lines may have multiple names separated by a space inside the square brackets, for example `[line-name-a line-name-b]`.

[`<length>`](length)  
Is a non-negative length.

[`<percentage>`](percentage)  
Is a non-negative [`<percentage>`](percentage) value, relative to the block size of the grid container. If the size of the grid container depends on the size of its tracks, then the percentage must be treated as `auto`.  
The intrinsic size contributions of the track may be adjusted to the size of the grid container, and increase the final size of the track by the minimum amount that would result in honoring the percentage.

[`<flex>`](flex_value)  
Is a non-negative dimension with the unit `fr` specifying the track’s flex factor. Each `<flex>`-sized track takes a share of the remaining space in proportion to its flex factor. When appearing outside a `minmax()` notation, it implies an automatic minimum (i.e. `minmax(auto, <flex>)`).

[`max-content`](max-content)  
Is a keyword representing the largest maximal content contribution of the grid items occupying the grid track.

[`min-content`](min-content)  
Is a keyword representing the largest minimal content contribution of the grid items occupying the grid track.

[`minmax(min, max)`](<minmax()>)  
Is a functional notation that defines a size range, greater than or equal to _min_, and less than or equal to _max_. If _max_ is smaller than _min_, then _max_ is ignored and the function is treated as _min_. As a maximum, a `<flex>` value sets the track’s flex factor. It is invalid as a minimum.

`auto`  
As a maximum represents the largest [`max-content`](max-content) size of the items in that track.

As a minimum represents the largest minimum size of items in that track (specified by the [`min-width`](min-width)/[`min-height`](min-height) of the items). This is often, though not always, the [`min-content`](min-content) size.

If used outside of [`minmax()`](<minmax()>) notation, `auto` represents the range between the minimum and maxium described above. This behaves similarly to `min-content(min-content,max-content)` in most cases.

**Note:**
`auto` track sizes (and only `auto` track sizes) can be stretched by the [`align-content`](align-content) and [`justify-content`](justify-content) properties. Therefore by default, an `auto` sized track will take up any remaining space in the grid container.

[`fit-content( [ <length> | <percentage> ] )`](<fit-content()>)  
Represents the formula `min(max-content, max(auto, argument))`, which is calculated similar to `auto` (i.e. `minmax(auto, max-content)`), except that the track size is clamped at argument if it is greater than the `auto` minimum.

[`repeat( [ <positive-integer> | auto-fill | auto-fit ] , <track-list> )`](<repeat()>)  
Represents a repeated fragment of the track list, allowing a large number of rows that exhibit a recurring pattern to be written in a more compact form.

`masonry`<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The masonry value indicates that this axis should be laid out according to the masonry algorithm.

`subgrid`  
The `subgrid` value indicates that the grid will adopt the spanned portion of its parent grid in that axis. Rather than being specified explicitly, the sizes of the grid rows/columns will be taken from the parent grid’s definition.

**Note**

The `masonry` value is from Level 3 of the Grid specification and currently only has an experimental implementation behind a flag in Firefox.

The `subgrid` value is from Level 2 of the Grid specification and currently only has implementation in Firefox 71 and onwards.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>grid containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to corresponding dimension of the content area</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr><tr class="even"><td>Animation type</td><td>simple list of length, percentage, or calc, provided the only differences are in the values of the length, percentage, or calc components in the list</td></tr></tbody></table>

## Formal syntax

    none | <track-list> | <auto-track-list> | subgrid <line-name-list>?where
    <track-list> = [ <line-names>? [ <track-size> | <track-repeat> ] ]+ <line-names>?
    <auto-track-list> = [ <line-names>? [ <fixed-size> | <fixed-repeat> ] ]* <line-names>? <auto-repeat>
    [ <line-names>? [ <fixed-size> | <fixed-repeat> ] ]* <line-names>?
    <line-name-list> = [ <line-names> | <name-repeat> ]+where
    <line-names> = '[' <custom-ident>* ']'
    <track-size> = <track-breadth> | minmax( <inflexible-breadth> , <track-breadth> ) | fit-content( [ <length> | <percentage> ] )
    <track-repeat> = repeat( [ [1,∞]> ] , [ <line-names>? <track-size> ]+ <line-names>? )
    <fixed-size> = <fixed-breadth> | minmax( <fixed-breadth> , <track-breadth> ) | minmax( <inflexible-breadth> , <fixed-breadth> )
    <fixed-repeat> = repeat( [ [1,∞]> ] , [ <line-names>? <fixed-size> ]+ <line-names>? )
    <auto-repeat> = repeat( [ auto-fill | auto-fit ] , [ <line-names>? <fixed-size> ]+ <line-names>? )where
    <track-breadth> = <length-percentage> | <flex> | min-content | max-content | auto
    <inflexible-breadth> = <length> | <percentage> | min-content | max-content | auto
    <fixed-breadth> = <length-percentage>
    where
    <length-percentage> = <length> | <percentage>

## Examples

### Specifying grid row sizes

#### HTML

    <div id="grid">
      <div id="areaA">A</div>
      <div id="areaB">B</div>
    </div>

#### CSS

    #grid {
      display: grid;
      height: 100px;
      grid-template-rows: 30px 1fr;
    }

    #areaA {
      background-color: lime;
    }

    #areaB {
      background-color: yellow;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid/#propdef-grid-template-rows">CSS Grid Layout<br />
<span class="small">The definition of 'grid-template-rows' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-grid-2/#subgrids">CSS Grid Layout Module Level 2<br />
<span class="small">The definition of 'subgrid' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds subgrid</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid-3/#masonry-layout">CSS Grid Layout Module Level 3<br />
<span class="small">The definition of 'masonry layout' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds masonry</td></tr></tbody></table>

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

`grid-template-rows`

57

16

12-79

52

10

44

10.1

57

57

52

43

10.3

6.0

`animation`

No

See [bug 759665](https://crbug.com/759665).

No

See [bug 759665](https://crbug.com/759665).

66

No

No

See [bug 759665](https://crbug.com/759665).

No

See [bug 204580](https://webkit.org/b/204580).

No

See [bug 759665](https://crbug.com/759665).

No

See [bug 759665](https://crbug.com/759665).

66

No

See [bug 759665](https://crbug.com/759665).

No

See [bug 204580](https://webkit.org/b/204580).

No

See [bug 759665](https://crbug.com/759665).

`fit-content`

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

`masonry`

No

No

77

No

No

No

No

No

No

No

No

No

`minmax`

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

`repeat`

57

16

76

57-76

`repeat(auto-fill, ...)` and `repeat(auto-fit, ...)` only support one repeated column (see [bug 1341507](https://bugzil.la/1341507)).

52-57

[`calc()`](https://developer.mozilla.org/docs/Web/CSS/calc) doesn't work in `repeat()` (see [bug 1350069](https://bugzil.la/1350069)).

No

44

10.1

57

57

79

57-79

`repeat(auto-fill, ...)` and `repeat(auto-fit, ...)` only support one repeated column (see [bug 1341507](https://bugzil.la/1341507)).

52-57

[`calc()`](https://developer.mozilla.org/docs/Web/CSS/calc) doesn't work in `repeat()` (see [bug 1350069](https://bugzil.la/1350069)).

43

10.3

6.0

`subgrid`

No

See [bug 618969](https://crbug.com/618969).

No

See [bug 618969](https://crbug.com/618969).

71

69

Enabled by default in Firefox Nightly.

No

No

See [bug 618969](https://crbug.com/618969).

No

See [bug 202115](https://webkit.org/b/202115).

No

See [bug 618969](https://crbug.com/618969).

No

See [bug 618969](https://crbug.com/618969).

No

No

See [bug 618969](https://crbug.com/618969).

No

See [bug 202115](https://webkit.org/b/202115).

No

See [bug 618969](https://crbug.com/618969).

## See also

- Related CSS properties: [`grid-template-columns`](grid-template-columns), [`grid-template-areas`](grid-template-areas), [`grid-template`](grid-template)
- Grid Layout Guide: _[Basic concepts of grid layout - Grid Tracks](css_grid_layout/basic_concepts_of_grid_layout#grid_tracks)_
- Video tutorial: _[Defining a Grid](https://gridbyexample.com/video/series-define-a-grid/)_
- [Subgrid](css_grid_layout/subgrid)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows</a>
