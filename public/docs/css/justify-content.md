# justify-content

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) `justify-content` property defines how the browser distributes space between and around content items along the [main-axis](https://developer.mozilla.org/en-US/docs/Glossary/Main_Axis) of a flex container, and the inline axis of a grid container.

The interactive example below demonstrates some of the values using Grid Layout.

The alignment is done after the lengths and auto margins are applied, meaning that, if in a [Flexbox layout](css_flexible_box_layout) there is at least one flexible element, with [`flex-grow`](flex-grow) different from `0`, it will have no effect as there won't be any available space.

## Syntax

    /* Positional alignment */
    justify-content: center;     /* Pack items around the center */
    justify-content: start;      /* Pack items from the start */
    justify-content: end;        /* Pack items from the end */
    justify-content: flex-start; /* Pack flex items from the start */
    justify-content: flex-end;   /* Pack flex items from the end */
    justify-content: left;       /* Pack items from the left */
    justify-content: right;      /* Pack items from the right */

    /* Baseline alignment */
    /* justify-content does not take baseline values */

    /* Normal alignment */
    justify-content: normal;

    /* Distributed alignment */
    justify-content: space-between; /* Distribute items evenly
                                       The first item is flush with the start,
                                       the last is flush with the end */
    justify-content: space-around;  /* Distribute items evenly
                                       Items have a half-size space
                                       on either end */
    justify-content: space-evenly;  /* Distribute items evenly
                                       Items have equal space around them */
    justify-content: stretch;       /* Distribute items evenly
                                       Stretch 'auto'-sized items to fit
                                       the container */

    /* Overflow alignment */
    justify-content: safe center;
    justify-content: unsafe center;

    /* Global values */
    justify-content: inherit;
    justify-content: initial;
    justify-content: unset;

### Values

`start`  
The items are packed flush to each other toward the start edge of the alignment container in the main axis.

`end`  
The items are packed flush to each other toward the end edge of the alignment container in the main axis.

`flex-start`  
The items are packed flush to each other toward the edge of the alignment container depending on the flex container's main-start side.  
This only applies to flex layout items. For items that are not children of a flex container, this value is treated like `start`.

`flex-end`  
The items are packed flush to each other toward the edge of the alignment container depending on the flex container's main-end side.  
This only applies to flex layout items. For items that are not children of a flex container, this value is treated like `end`.

`center`  
The items are packed flush to each other toward the center of the alignment container along the main axis.

`left`  
The items are packed flush to each other toward the left edge of the alignment container. If the property’s axis is not parallel with the inline axis, this value behaves like `start`.

`right`  
The items are packed flush to each other toward the right edge of the alignment container in the appropriate axis. If the property’s axis is not parallel with the inline axis, this value behaves like `start`.

`normal`  
The items are packed in their default position as if no `justify-content` value was set. This value behaves as `stretch` in grid and flex containers.

`baseline first baseline`  
`last baseline`  
Specifies participation in first- or last-baseline alignment: aligns the alignment baseline of the box’s first or last baseline set with the corresponding baseline in the shared first or last baseline set of all the boxes in its baseline-sharing group.  
The fallback alignment for `first baseline` is `start`, the one for `last baseline` is `end`.

`space-between`  
The items are evenly distributed within the alignment container along the main axis. The spacing between each pair of adjacent items is the same. The first item is flush with the main-start edge, and the last item is flush with the main-end edge.

`space-around`  
The items are evenly distributed within the alignment container along the main axis. The spacing between each pair of adjacent items is the same. The empty space before the first and after the last item equals half of the space between each pair of adjacent items.

`space-evenly`  
The items are evenly distributed within the alignment container along the main axis. The spacing between each pair of adjacent items, the main-start edge and the first item, and the main-end edge and the last item, are all exactly the same.

`stretch`  
If the combined size of the items along the main axis is less than the size of the alignment container, any `auto`-sized items have their size increased equally (not proportionally), while still respecting the constraints imposed by [`max-height`](max-height)/[`max-width`](max-width) (or equivalent functionality), so that the combined size exactly fills the alignment container along the main axis.

**Note:** `stretch` is not supported by flexible boxes (flexbox).

`safe`  
Used alongside an alignment keyword. If the chosen keyword means that the item overflows the alignment container causing data loss, the item is instead aligned as if the alignment mode were `start`.

`unsafe`  
Used alongside an alignment keyword. Regardless of the relative sizes of the item and alignment container, and regardless of whether overflow which causes data loss might happen, the given alignment value is honored.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>flex containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | <content-distribution> | <overflow-position>? [ <content-position> | left | right ]where
    <content-distribution> = space-between | space-around | space-evenly | stretch
    <overflow-position> = unsafe | safe
    <content-position> = center | start | end | flex-start | flex-end

## Examples

### Setting flex item distribution

#### CSS

    #container {
      display: flex;
      justify-content: space-between; /* Can be changed in the live sample */
    }

    #container > div {
      width: 100px;
      height: 100px;
      background: linear-gradient(-45deg, #788cff, #b4c8ff);
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-align-3/#propdef-justify-content">CSS Box Alignment Module Level 3<br />
<span class="small">The definition of 'justify-content' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the [ first | last ]? baseline, self-start, self-end, start, end, left, right, unsafe | safe values.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-flexbox-1/#propdef-justify-content">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'justify-content' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`justify-content`

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

`justify-content`

52

29

Older versions of the specification treat absolute positioned children as though they are a 0 by 0 flex item. Later specification versions take the children out of the flow and set their positions based on align and justify properties. Chrome implements the new behavior beginning with Chrome 52.

21

12

12

20

Before Firefox 27, Firefox supported only single-line flexbox.

49

11

12.1

9

6.1

52

4.4

Older versions of the specification treat absolute positioned children as though they are a 0 by 0 flex item. Later specification versions take the children out of the flow and set their positions based on align and justify properties. Chrome implements the new behavior beginning with Chrome 52.

≤37

52

29

Older versions of the specification treat absolute positioned children as though they are a 0 by 0 flex item. Later specification versions take the children out of the flow and set their positions based on align and justify properties. Chrome implements the new behavior beginning with Chrome 52.

25

20

Before Firefox 27, Firefox supported only single-line flexbox.

49

12.1

9

6.1

6.0

2.0

Older versions of the specification treat absolute positioned children as though they are a 0 by 0 flex item. Later specification versions take the children out of the flow and set their positions based on align and justify properties. Chrome implements the new behavior beginning with Chrome 52.

1.5

`baseline`

57

79

45-60

`justify-content` no longer accepts baseline values

No

44

No

57

57

45-60

`justify-content` no longer accepts baseline values

43

No

7.0

`first_last_baseline`

No

No

52-60

`justify-content` no longer accepts baseline values

No

No

No

No

No

52-60

`justify-content` no longer accepts baseline values

No

No

No

`left_right`

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

52

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

9

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

52

No

This value is recognized, but has no effect.

9

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

9

No

This value is recognized, but has no effect.

No

This value is recognized, but has no effect.

45

No

This value is recognized, but has no effect.

9

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content</a>
