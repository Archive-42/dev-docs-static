# align-content

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) `align-content` property sets the distribution of space between and around content items along a [flexbox](css_flexible_box_layout)'s cross-axis or a [grid](css_grid_layout)'s block axis.

The interactive example below use Grid Layout to demonstrate some of the values of this property.

This property has no effect on single line flex containers (i.e. ones with `flex-wrap: nowrap`).

## Syntax

    /* Basic positional alignment */
    /* align-content does not take left and right values */
    align-content: center;     /* Pack items around the center */
    align-content: start;      /* Pack items from the start */
    align-content: end;        /* Pack items from the end */
    align-content: flex-start; /* Pack flex items from the start */
    align-content: flex-end;   /* Pack flex items from the end */

    /* Normal alignment */
    align-content: normal;

    /* Baseline alignment */
    align-content: baseline;
    align-content: first baseline;
    align-content: last baseline;

    /* Distributed alignment */
    align-content: space-between; /* Distribute items evenly
                                     The first item is flush with the start,
                                     the last is flush with the end */
    align-content: space-around;  /* Distribute items evenly
                                     Items have a half-size space
                                     on either end */
    align-content: space-evenly;  /* Distribute items evenly
                                     Items have equal space around them */
    align-content: stretch;       /* Distribute items evenly
                                     Stretch 'auto'-sized items to fit
                                     the container */

    /* Overflow alignment */
    align-content: safe center;
    align-content: unsafe center;

    /* Global values */
    align-content: inherit;
    align-content: initial;
    align-content: unset;

### Values

`start`  
The items are packed flush to each other against the start edge of the alignment container in the cross axis.

`end`  
The items are packed flush to each other against the end edge of the alignment container in the cross axis.

`flex-start`  
The items are packed flush to each other against the edge of the alignment container depending on the flex container's cross-start side.  
This only applies to flex layout items. For items that are not children of a flex container, this value is treated like `start`.

`flex-end`  
The items are packed flush to each other against the edge of the alignment container depending on the flex container's cross-end side.  
This only applies to flex layout items. For items that are not children of a flex container, this value is treated like `end`.

`center`  
The items are packed flush to each other in the center of the alignment container along the cross axis.

`normal`  
The items are packed in their default position as if no `align-content` value was set.

`baseline first baseline`  
`last baseline`  
<img src="data:image/png;base64,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" alt="the baseline is the line upon which most letters &quot;sit&quot; and below which descenders extend." width="410" height="110" />

Specifies participation in first- or last-baseline alignment: aligns the alignment baseline of the box’s first or last baseline set with the corresponding baseline in the shared first or last baseline set of all the boxes in its baseline-sharing group.  
The fallback alignment for `first baseline` is `start`, the one for `last baseline` is `end`.

`space-between`  
The items are evenly distributed within the alignment container along the cross axis. The spacing between each pair of adjacent items is the same. The first item is flush with the start edge of the alignment container in the cross axis, and the last item is flush with the end edge of the alignment container in the cross axis.

`space-around`  
The items are evenly distributed within the alignment container along the cross axis. The spacing between each pair of adjacent items is the same. The empty space before the first and after the last item equals half of the space between each pair of adjacent items.

`space-evenly`  
The items are evenly distributed within the alignment container along the cross axis. The spacing between each pair of adjacent items, the start edge and the first item, and the end edge and the last item, are all exactly the same.

`stretch`  
If the combined size of the items along the cross axis is less than the size of the alignment container, any `auto`-sized items have their size increased equally (not proportionally), while still respecting the constraints imposed by [`max-height`](max-height)/[`max-width`](max-width) (or equivalent functionality), so that the combined size exactly fills the alignment container along the cross axis.

`safe`  
Used alongside an alignment keyword. If the chosen keyword means that the item overflows the alignment container causing data loss, the item is instead aligned as if the alignment mode were `start`.

`unsafe`  
Used alongside an alignment keyword. Regardless of the relative sizes of the item and alignment container and whether overflow which causes data loss might happen, the given alignment value is honored.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>multi-line flex containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | <baseline-position> | <content-distribution> | <overflow-position>? <content-position>where
    <baseline-position> = [ first | last ]? baseline
    <content-distribution> = space-between | space-around | space-evenly | stretch
    <overflow-position> = unsafe | safe
    <content-position> = center | start | end | flex-start | flex-end

## Examples

### CSS

    #container {
      height:200px;
      width: 240px;
      align-content: center; /* Can be changed in the live sample */
      background-color: #8c8c8c;
    }

    .flex {
      display: flex;
      flex-wrap: wrap;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, 50px);
    }

    div > div {
      box-sizing: border-box;
      border: 2px solid #8c8c8c;
      width: 50px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    #item1 {
      background-color: #8cffa0;
      min-height: 30px;
    }

    #item2 {
      background-color: #a0c8ff;
      min-height: 50px;
    }

    #item3 {
      background-color: #ffa08c;
      min-height: 40px;
    }

    #item4 {
      background-color: #ffff8c;
      min-height: 60px;
    }

    #item5 {
      background-color: #ff8cff;
      min-height: 70px;
    }

    #item6 {
      background-color: #8cffff;
      min-height: 50px;
      font-size: 30px;
    }

    select {
      font-size: 16px;
    }

    .row {
      margin-top: 10px;
    }

### HTML

    <div id="container" class="flex">
      <div id="item1">1</div>
      <div id="item2">2</div>
      <div id="item3">3</div>
      <div id="item4">4</div>
      <div id="item5">5</div>
      <div id="item6">6</div>
    </div>

    <div class="row">
      <label for="display">display: </label>
      <select id="display">
        <option value="flex">flex</option>
        <option value="grid">grid</option>
      </select>
    </div>

    <div class="row">
      <label for="values">align-content: </label>
      <select id="values">
        <option value="normal">normal</option>
        <option value="stretch">stretch</option>
        <option value="flex-start">flex-start</option>
        <option value="flex-end">flex-end</option>
        <option value="center" selected>center</option>
        <option value="space-between">space-between</option>
        <option value="space-around">space-around</option>
        <option value="space-evenly">space-evenly</option>

        <option value="start">start</option>
        <option value="end">end</option>
        <option value="left">left</option>
        <option value="right">right</option>

        <option value="baseline">baseline</option>
        <option value="first baseline">first baseline</option>
        <option value="last baseline">last baseline</option>

        <option value="safe center">safe center</option>
        <option value="unsafe center">unsafe center</option>
        <option value="safe right">safe right</option>
        <option value="unsafe right">unsafe right</option>
        <option value="safe end">safe end</option>
        <option value="unsafe end">unsafe end</option>
        <option value="safe flex-end">safe flex-end</option>
        <option value="unsafe flex-end">unsafe flex-end</option>
      </select>
    </div>

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-align-3/#propdef-align-content">CSS Box Alignment Module Level 3<br />
<span class="small">The definition of 'align-content' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the [ first | last ]? baseline, start, end, left, right, unsafe | safe values.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-flexbox-1/#align-content-property">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'align-content' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>multi-line flex containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

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

`align-content`

57

16

52

No

44

10.1

57

52

52

43

10.3

6.2

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

`align-content`

29

21

12

12

28

49

11

12.1

9

6.1

4.4

≤37

29

25

28

49

12.1

9

7

2.0

1.5

`baseline`

57

79

45

No

44

9

57

57

45

43

9

7.0

`first_last_baseline`

No

No

52

No

No

11

No

No

52

No

11

No

`left_right`

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

52-60

`align-content` no longer accepts the `left` and `right` values

No

No

This value is recognized, but has no effect.

No

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

52-60

`align-content` no longer accepts the `left` and `right` values

No

This value is recognized, but has no effect.

No

No

This value is recognized, but has no effect.

`safe_unsafe`

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

63

No

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

63

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

`space-evenly`

60

79

52

No

47

11

60

60

52

44

11

8.0

`start_end`

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

45

No

No

This value is recognized, but has no effect.

No

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

45

No

This value is recognized, but has no effect.

No

No

This value is recognized, but has no effect.

`stretch`

57

79

52

No

44

9

57

57

52

43

9

7.0

BCD tables only load in the browser

### Support in Grid layout

BCD tables only load in the browser

## See also

- CSS Flexbox Guide: _[Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)_
- CSS Flexbox Guide: _[Aligning items in a flex container](css_flexible_box_layout/aligning_items_in_a_flex_container)_
- CSS Grid Guide: _[Box alignment in CSS Grid layouts](css_grid_layout/box_alignment_in_css_grid_layout)_
- [CSS Box Alignment](css_box_alignment)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/align-content" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/align-content</a>
