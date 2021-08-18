# align-items

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) `align-items` property sets the [`align-self`](align-self) value on all direct children as a group. In Flexbox, it controls the alignment of items on the [Cross Axis](https://developer.mozilla.org/en-US/docs/Glossary/Cross_Axis). In Grid Layout, it controls the alignment of items on the Block Axis within their [grid area](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas).

The interactive example below demonstrates some of the values for `align-items` using grid layout.

## Syntax

    /* Basic keywords */
    align-items: normal;
    align-items: stretch;

    /* Positional alignment */
    /* align-items does not take left and right values */
    align-items: center; /* Pack items around the center */
    align-items: start; /* Pack items from the start */
    align-items: end; /* Pack items from the end */
    align-items: flex-start; /* Pack flex items from the start */
    align-items: flex-end; /* Pack flex items from the end */

    /* Baseline alignment */
    align-items: baseline;
    align-items: first baseline;
    align-items: last baseline; /* Overflow alignment (for positional alignment only) */
    align-items: safe center;
    align-items: unsafe center;

    /* Global values */
    align-items: inherit;
    align-items: initial;
    align-items: unset;

### Values

`normal`  
The effect of this keyword is dependent of the layout mode we are in:

- In absolutely-positioned layouts, the keyword behaves like `start` on _replaced_ absolutely-positioned boxes, and as `stretch` on _all other_ absolutely-positioned boxes.
- In static position of absolutely-positioned layouts, the keyword behaves as `stretch`.
- For flex items, the keyword behaves as `stretch`.
- For grid items, this keyword leads to a behavior similar to the one of `stretch`, except for boxes with an aspect ratio or an intrinsic sizes where it behaves like `start`.
- The property doesn't apply to block-level boxes, and to table cells.

`flex-start`  
The cross-start margin edges of the flex items are flushed with the cross-start edge of the line.

`flex-end`  
The cross-end margin edges of the flex items are flushed with the cross-end edge of the line.

`center`  
The flex items' margin boxes are centered within the line on the cross-axis. If the cross-size of an item is larger than the flex container, it will overflow equally in both directions.

`start`  
The items are packed flush to each other toward the start edge of the alignment container in the appropriate axis.

`end`  
The items are packed flush to each other toward the end edge of the alignment container in the appropriate axis.

`self-start`  
The items are packed flush to the edge of the alignment container of the start side of the item, in the appropriate axis.

`self-end`  
The items are packed flush to the edge of the alignment container of the end side of the item, in the appropriate axis.

`baseline`  
`first baseline`  
`last baseline`  
All flex items are aligned such that their [flex container baselines](https://drafts.csswg.org/css-flexbox-1/#flex-baselines) align. The item with the largest distance between its cross-start margin edge and its baseline is flushed with the cross-start edge of the line.

`stretch`  
Flex items are stretched such that the cross-size of the item's margin box is the same as the line while respecting width and height constraints.

`safe`  
Used alongside an alignment keyword. If the chosen keyword means that the item overflows the alignment container causing data loss, the item is instead aligned as if the alignment mode were `start`.

`unsafe`  
Used alongside an alignment keyword. Regardless of the relative sizes of the item and alignment container and whether overflow which causes data loss might happen, the given alignment value is honored.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | stretch | <baseline-position> | [ <overflow-position>? <self-position> ]where
    <baseline-position> = [ first | last ]? baseline
    <overflow-position> = unsafe | safe
    <self-position> = center | start | end | self-start | self-end | flex-start | flex-end

## Examples

### CSS

    #container {
      height:200px;
      width: 240px;
      align-items: center; /* Can be changed in the live sample */
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
      <label for="values">align-items: </label>
      <select id="values">
        <option value="normal">normal</option>
        <option value="flex-start">flex-start</option>
        <option value="flex-end">flex-end</option>
        <option value="center" selected>center</option>
        <option value="baseline">baseline</option>
        <option value="stretch">stretch</option>

        <option value="start">start</option>
        <option value="end">end</option>
        <option value="self-start">self-start</option>
        <option value="self-end">self-end</option>
        <option value="left">left</option>
        <option value="right">right</option>

        <option value="first baseline">first baseline</option>
        <option value="last baseline">last baseline</option>

        <option value="safe center">safe center</option>
        <option value="unsafe center">unsafe center</option>
        <option value="safe right">safe right</option>
        <option value="unsafe right">unsafe right</option>
        <option value="safe end">safe end</option>
        <option value="unsafe end">unsafe end</option>
        <option value="safe self-end">safe self-end</option>
        <option value="unsafe self-end">unsafe self-end</option>
        <option value="safe flex-end">safe flex-end</option>
        <option value="unsafe flex-end">unsafe flex-end</option>
      </select>
    </div>

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-align-3/#propdef-align-items">CSS Box Alignment Module Level 3<br />
<span class="small">The definition of 'align-items' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Update to latest syntax definitions.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-flexbox-1/#propdef-align-items">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'align-items' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`align-items`

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

`start_end`

57

79

52

No

44

11

57

57

52

43

11

7.0

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

`align-items`

52

29

Older versions of the specification treat absolute positioned children as though they are a 0 by 0 flex item. Later specification versions take the children out of the flow and set their positions based on align and justify properties. Chrome implements the new behavior beginning with Chrome 52.

21

12

12

20

Multi-line flexbox has been supported since Firefox 28.

49

11

In Internet Explorer 10 and 11, if column flex items have `align-items: center;` set on them and their content is too large, then they will overflow the bounds of their container. See [Flexbug \#2](https://github.com/philipwalton/flexbugs#2-column-flex-items-set-to-align-itemscenter-overflow-their-container).

12.1

9

7

52

4.4

Older versions of the specification treat absolute positioned children as though they are a 0 by 0 flex item. Later specification versions take the children out of the flow and set their positions based on align and justify properties. Chrome implements the new behavior beginning with Chrome 52.

≤37

52

29

Older versions of the specification treat absolute positioned children as though they are a 0 by 0 flex item. Later specification versions take the children out of the flow and set their positions based on align and justify properties. Chrome implements the new behavior beginning with Chrome 52.

25

20

Multi-line flexbox has been supported since Firefox 28.

49

12.1

9

7

6.0

2.0

Older versions of the specification treat absolute positioned children as though they are a 0 by 0 flex item. Later specification versions take the children out of the flow and set their positions based on align and justify properties. Chrome implements the new behavior beginning with Samsung Internet 6.0.

1.5

`first_last_baseline`

59

79

45

No

46

11

59

59

45

43

11

7.0

`left_right`

No

No

45

No

No

9

No

No

45

No

9

No

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

`start_end`

No

No

45

No

44

No

No

No

45

43

No

No

BCD tables only load in the browser

### Support in Grid layout

BCD tables only load in the browser

## See also

- CSS Flexbox Guide: _[Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)_
- CSS Flexbox Guide: _[Aligning items in a flex container](css_flexible_box_layout/aligning_items_in_a_flex_container)_
- CSS Grid Guide: _[Box alignment in CSS Grid layouts](css_grid_layout/box_alignment_in_css_grid_layout)_
- [CSS Box Alignment](css_box_alignment)
- The [`align-self`](align-self) property

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/align-items" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/align-items</a>
