# align-self

The `align-self` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property overrides a grid or flex item's [`align-items`](align-items) value. In Grid, it aligns the item inside the [grid area](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas). In Flexbox, it aligns the item on the [cross axis](https://developer.mozilla.org/en-US/docs/Glossary/Cross_Axis).

The property doesn't apply to block-level boxes, or to table cells. If a flexbox item's cross-axis margin is `auto`, then `align-self` is ignored.

## Syntax

    /* Keyword values */
    align-self: auto;
    align-self: normal;

    /* Positional alignment */
    /* align-self does not take left and right values */
    align-self: center; /* Put the item around the center */
    align-self: start; /* Put the item at the start */
    align-self: end; /* Put the item at the end */
    align-self: self-start; /* Align the item flush at the start */
    align-self: self-end; /* Align the item flush at the end */
    align-self: flex-start; /* Put the flex item at the start */
    align-self: flex-end; /* Put the flex item at the end */

    /* Baseline alignment */
    align-self: baseline;
    align-self: first baseline;
    align-self: last baseline;
    align-self: stretch; /* Stretch 'auto'-sized items to fit the container */

    /* Overflow alignment */
    align-self: safe center;
    align-self: unsafe center;

    /* Global values */
    align-self: inherit;
    align-self: initial;
    align-self: unset;

### Values

`auto`  
Computes to the parent's [`align-items`](align-items) value.

`normal`  
The effect of this keyword is dependent of the layout mode we are in:

- In absolutely-positioned layouts, the keyword behaves like `start` on _replaced_ absolutely-positioned boxes, and as `stretch` on _all other_ absolutely-positioned boxes.
- In static position of absolutely-positioned layouts, the keyword behaves as `stretch`.
- For flex items, the keyword behaves as `stretch`.
- For grid items, this keyword leads to a behavior similar to the one of `stretch`, except for boxes with an aspect ratio or an intrinsic sizes where it behaves like `start`.
- The property doesn't apply to block-level boxes, and to table cells.

`self-start`  
Aligns the items to be flush with the edge of the alignment container corresponding to the item's start side in the cross axis.

`self-end`  
Aligns the items to be flush with the edge of the alignment container corresponding to the item's end side in the cross axis.

`flex-start`  
The cross-start margin edge of the flex item is flushed with the cross-start edge of the line.

`flex-end`  
The cross-end margin edge of the flex item is flushed with the cross-end edge of the line.

`center`  
The flex item's margin box is centered within the line on the cross-axis. If the cross-size of the item is larger than the flex container, it will overflow equally in both directions.

`baseline first baseline`  
`last baseline`  
Specifies participation in first- or last-baseline alignment: aligns the alignment baseline of the box’s first or last baseline set with the corresponding baseline in the shared first or last baseline set of all the boxes in its baseline-sharing group.  
The fallback alignment for `first baseline` is `start`, the one for `last baseline` is `end`.

`stretch`  
If the combined size of the items along the cross axis is less than the size of the alignment container and the item is `auto`-sized, its size is increased equally (not proportionally), while still respecting the constraints imposed by [`max-height`](max-height)/[`max-width`](max-width) (or equivalent functionality), so that the combined size of all `auto`-sized items exactly fills the alignment container along the cross axis.

`safe`  
If the size of the item overflows the alignment container, the item is instead aligned as if the alignment mode were `start`.

`unsafe`  
Regardless of the relative sizes of the item and alignment container, the given alignment value is honored.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>flex items, grid items, and absolutely-positioned boxes</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td><code>auto</code> computes to itself on absolutely-positioned elements, and to the computed value of <a href="align-items"><code>align-items</code></a> on the parent (minus any legacy keywords) on all other boxes, or <code>start</code> if the box has no parent. Its behavior depends on the layout model, as described for <a href="justify-self"><code>justify-self</code></a>. Otherwise the specified value.</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | normal | stretch | <baseline-position> | <overflow-position>? <self-position>where
    <baseline-position> = [ first | last ]? baseline
    <overflow-position> = unsafe | safe
    <self-position> = center | start | end | self-start | self-end | flex-start | flex-end

## Examples

### HTML

    <section>
      <div>Item #1</div>
      <div>Item #2</div>
      <div>Item #3</div>
    </section>

### CSS

    section {
      display: flex;
      align-items: center;
      height: 120px;
      background: beige;
    }

    div {
      height: 60px;
      background: cyan;
      margin: 5px;
    }

    div:nth-child(3) {
      align-self: flex-end;
      background: pink;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-align-3/#propdef-align-self">CSS Box Alignment Module Level 3<br />
<span class="small">The definition of 'align-self' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Update to latest syntax definitions.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-flexbox-1/#propdef-align-self">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'align-self' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`align-self`

57

16

52

10

Internet Explorer 10 and 11 have the property `-ms-grid-row-align`, which acts in a similar way to `align-self`.

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

`align-self`

36

29

Older versions of the specification treat absolute positioned children as though they are a 0 by 0 flex item. Later specification versions take the children out of the flow and set their positions based on align and justify properties. Chrome implements the new behavior beginning with Chrome 52.

21

12

20

Before Firefox 27, only single-line flexbox is supported.

49

11

12.1

9

6.1

37

4.4

Older versions of the specification treat absolute positioned children as though they are a 0 by 0 flex item. Later specification versions take the children out of the flow and set their positions based on align and justify properties. Chrome implements the new behavior beginning with Chrome 52.

≤37

36

29

Older versions of the specification treat absolute positioned children as though they are a 0 by 0 flex item. Later specification versions take the children out of the flow and set their positions based on align and justify properties. Chrome implements the new behavior beginning with Chrome 52.

25

20

Before Firefox 27, only single-line flexbox is supported.

49

12.1

9

6.1

3.0

2.0

Older versions of the specification treat absolute positioned children as though they are a 0 by 0 flex item. Later specification versions take the children out of the flow and set their positions based on align and justify properties. Chrome implements the new behavior beginning with Samsung Internet 6.0.

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

57

79

52

No

44

11.1

57

57

52

43

11.3

7.0

`left_right`

No

No

52

No

No

No

No

No

52

No

No

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
- The [`align-items`](align-items) property

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/align-self" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/align-self</a>
