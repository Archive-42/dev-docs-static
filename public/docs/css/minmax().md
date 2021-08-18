# minmax()

The `minmax()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) defines a size range greater than or equal to min and less than or equal to max. It is used with [CSS Grids](css_grid_layout).

## Syntax

    /* <inflexible-breadth>, <track-breadth> values */
    minmax(200px, 1fr)
    minmax(400px, 50%)
    minmax(30%, 300px)
    minmax(100px, max-content)
    minmax(min-content, 400px)
    minmax(max-content, auto)
    minmax(auto, 300px)
    minmax(min-content, auto)

    /* <fixed-breadth>, <track-breadth> values */
    minmax(200px, 1fr)
    minmax(30%, 300px)
    minmax(400px, 50%)
    minmax(50%, min-content)
    minmax(300px, max-content)
    minmax(200px, auto)

    /* <inflexible-breadth>, <fixed-breadth> values */
    minmax(400px, 50%)
    minmax(30%, 300px)
    minmax(min-content, 200px)
    minmax(max-content, 200px)
    minmax(auto, 300px)

A function taking two parameters, _min_ and _max_.

Each parameter can be a `<length>`, a `<percentage>`, a `<flex>` value, or one of the keyword values `max-content`, `min-content`, or `auto`.

If max &lt; min, then max is ignored and `minmax(min,max)` is treated as min. As a maximum, a [`<flex>`](flex_value) value sets the flex factor of a grid track; it is invalid as a minimum.

### Values

[`<length>`](length)  
A non-negative length.

[`<percentage>`](percentage)  
A non-negative percentage relative to the inline size of the grid container in column grid tracks, and the block size of the grid container in row grid tracks. If the size of the grid container depends on the size of its tracks, then the `<percentage>` must be treated as `auto`. The [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) may adjust the intrinsic size contributions of the track to the size of the grid container and increase the final size of the track by the minimum amount that would result in honoring the percentage.

[`<flex>`](flex_value)  
A non-negative dimension with the unit `fr` specifying the track’s flex factor. Each `<flex>`-sized track takes a share of the remaining space in proportion to its flex factor.

`max-content`  
Represents the largest max-content contribution of the grid items occupying the grid track.

`min-content`  
Represents the largest min-content contribution of the grid items occupying the grid track.

`auto`  
As a maximum, identical to `max-content`. As a minimum it represents the largest minimum size (as specified by [`min-width`](min-width)/[`min-height`](min-height)) of the grid items occupying the grid track.

### Formal syntax

    minmax( [ <length> | <percentage> | min-content | max-content | auto ] , [ <length> | <percentage> | <flex> | min-content | max-content | auto ] )

### CSS properties

`minmax()` function can be used within:

- [grid-template-columns](grid-template-columns)
- [grid-template-rows](grid-template-rows)
- [grid-auto-columns](grid-auto-columns)
- [grid-auto-rows](grid-auto-rows)

## Examples

### CSS

    #container {
      display: grid;
      grid-template-columns: minmax(min-content, 300px) minmax(200px, 1fr) 150px;
      grid-gap: 5px;
      box-sizing: border-box;
      height: 200px;
      width: 100%;
      background-color: #8cffa0;
      padding: 10px;
    }

    #container > div {
      background-color: #8ca0ff;
      padding: 5px;
    }

### HTML

    <div id="container">
      <div>
        Item as wide as the content, but at most 300 pixels.
      </div>
      <div>
        Item with flexible width but a minimum of 200 pixels.
      </div>
      <div>
        Inflexible item of 150 pixels width.
      </div>
    </div>

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid/#valdef-grid-template-columns-minmax">CSS Grid Layout<br />
<span class="small">The definition of 'minmax()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`minmax()`

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

- Grid Layout Guide: _[Basic concepts of grid layout - track sizing with minmax()](<css_grid_layout/basic_concepts_of_grid_layout#track_sizing_and_minmax()>)_
- [CSS grids, logical values and writing modes](css_grid_layout/css_grid_logical_values_and_writing_modes)
- Video tutorial: _[Introducing minmax()](https://gridbyexample.com/video/series-minmax/)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/minmax()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/minmax()</a>
