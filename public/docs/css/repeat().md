# repeat()

The `repeat()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) represents a repeated fragment of the track list, allowing a large number of columns or rows that exhibit a recurring pattern to be written in a more compact form.

This function can be used in the CSS Grid properties [`grid-template-columns`](grid-template-columns) and [`grid-template-rows`](grid-template-rows).

    /* <track-repeat> values */
    repeat(4, 1fr)
    repeat(4, [col-start] 250px [col-end])
    repeat(4, [col-start] 60% [col-end])
    repeat(4, [col-start] 1fr [col-end])
    repeat(4, [col-start] min-content [col-end])
    repeat(4, [col-start] max-content [col-end])
    repeat(4, [col-start] auto [col-end])
    repeat(4, [col-start] minmax(100px, 1fr) [col-end])
    repeat(4, [col-start] fit-content(200px) [col-end])
    repeat(4, 10px [col-start] 30% [col-middle] auto [col-end])
    repeat(4, [col-start] min-content [col-middle] max-content [col-end])

    /* <auto-repeat> values */
    repeat(auto-fill, 250px)
    repeat(auto-fit, 250px)
    repeat(auto-fill, [col-start] 250px [col-end])
    repeat(auto-fit, [col-start] 250px [col-end])
    repeat(auto-fill, [col-start] minmax(100px, 1fr) [col-end])
    repeat(auto-fill, 10px [col-start] 30% [col-middle] 400px [col-end])

    /* <fixed-repeat> values */
    repeat(4, 250px)
    repeat(4, [col-start] 250px [col-end])
    repeat(4, [col-start] 60% [col-end])
    repeat(4, [col-start] minmax(100px, 1fr) [col-end])
    repeat(4, [col-start] fit-content(200px) [col-end])
    repeat(4, 10px [col-start] 30% [col-middle] 400px [col-end])

## Syntax

### Values

[`<length>`](length)  
A positive integer length.

[`<percentage>`](percentage)  
A non-negative percentage relative to the inline size of the grid container in column grid tracks, and the block size of the grid container in row grid tracks. If the size of the grid container depends on the size of its tracks, then the `<percentage>` must be treated as `auto`. The user-agent may adjust the intrinsic size contributions of the track to the size of the grid container and increase the final size of the track by the minimum amount that would result in honoring the percentage.

[`<flex>`](flex_value)  
A non-negative dimension with the unit `fr` specifying the track’s flex factor. Each `<flex>`-sized track takes a share of the remaining space in proportion to its flex factor.

`max-content`  
Represents the largest max-content contribution of the grid items occupying the grid track.

`min-content`  
Represents the largest min-content contribution of the grid items occupying the grid track.

`auto`  
As a maximum, identical to `max-content`. As a minimum it represents the largest minimum size (as specified by [`min-width`](min-width)/[`min-height`](min-height)) of the grid items occupying the grid track.

`auto-fill`  
If the grid container has a definite or maximal size in the relevant axis, then the number of repetitions is the largest possible positive integer that does not cause the grid to overflow its grid container. Treating each track as its maximal track sizing function (each independent value used to define `grid-template-rows` or `grid-template-columns`), if that is definite. Otherwise, as its minimum track sizing function, and taking grid-gap into account. If any number of repetitions would overflow, then the repetition is `1`. Otherwise, if the grid container has a definite minimal size in the relevant axis, the number of repetitions is the smallest possible positive integer that fulfills that minimum requirement. Otherwise, the specified track list repeats only once.

`auto-fit`  
Behaves the same as `auto-fill`, except that after placing the grid items any empty repeated tracks are collapsed. An empty track is one with no in-flow grid items placed into or spanning across it. (This can result in all tracks being collapsed, if they’re all empty.)

A collapsed track is treated as having a single fixed track sizing function of `0px`, and the gutters on either side of it collapse.

For the purpose of finding the number of auto-repeated tracks, the user agent floors the track size to a user agent specified value (e.g., `1px`), to avoid division by zero.

## Examples

### Specifying grid columns using repeat()

#### HTML

    <div id="container">
      <div>
        This item is 50 pixels wide.
      </div>
      <div>
        Item with flexible width.
      </div>
      <div>
        This item is 50 pixels wide.
      </div>
      <div>
        Item with flexible width.
      </div>
      <div>
        Inflexible item of 100 pixels width.
      </div>
    </div>

#### CSS

    #container {
      display: grid;
      grid-template-columns: repeat(2, 50px 1fr) 100px;
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

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid/#funcdef-repeat">CSS Grid Layout<br />
<span class="small">The definition of 'repeat()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`repeat()`

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

## See also

- Related CSS properties: [`grid-template`](grid-template), [`grid-template-rows`](grid-template-rows), [`grid-template-columns`](grid-template-columns), [`grid-template-areas`](grid-template-areas), [`grid-auto-columns`](grid-auto-columns), [`grid-auto-rows`](grid-auto-rows), [`grid-auto-flow`](grid-auto-flow)
- Grid Layout Guide: _[Line-based placement with CSS Grid](css_grid_layout/line-based_placement_with_css_grid)_
- Grid Layout Guide: _[Grid template areas - Grid definition shorthands](css_grid_layout/grid_template_areas#grid_definition_shorthands)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/repeat()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/repeat()</a>
