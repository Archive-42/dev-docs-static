# CSS Box Alignment

The CSS Box Alignment module specifies CSS features that relate to the alignment of boxes in the various CSS box layout models: block layout, table layout, flex layout, and grid layout. The module aims to create a consistent method of alignment across all of CSS. This document details the general concepts found in the specification.

**Note**: The documentation for each layout method will detail how Box Alignment is applied there.

## Older alignment methods

CSS traditionally had very limited alignment capabilities. We were able to align text using [`text-align`](text-align), center blocks using auto [`margin`](margin)s, and in table or inline-block layouts using the [`vertical-align`](vertical-align) property. Alignment of text is now covered by the [Inline Layout](https://www.w3.org/TR/css-inline-3/) and [CSS Text](https://www.w3.org/TR/css-text-3/) modules, and for the first time in Box Alignment we have full horizontal and vertical alignment capabilities.

If you initially learned [Flexbox](css_flexible_box_layout) then you may consider these properties to be part of the Flexbox specification, and some of the properties are indeed listed in Level 1 of Flexbox. However the specification notes that the Box Alignment specification should be referred to as it may add additional capabilities over what is currently in Flexbox.

## Basic examples

The following examples demonstrate how some of the Box Alignment Properties are applied in [Grid](css_grid_layout) and [Flexbox](css_flexible_box_layout).

### CSS grid layout alignment example

In this example using Grid Layout, there is extra space in the grid container after laying out the fixed width tracks on the inline (main) axis. This space is distributed using [`justify-content`](justify-content). On the block (cross) axis the alignment of the items inside their grid areas is controlled with [`align-items`](align-items). The first item overrides the `align-items` value set on the group by setting [`align-self`](align-self) to `center`.

### Flexbox Alignment Example

In this example, three flex items are aligned on the main axis using `justify-content` and on the Cross Axis using `align-items`. The first item overrides the `align-items` set on the group by setting `align-self` to `center`.

## Key concepts and terminology

The specification details some alignment terminology to make it easier to discuss these alignment properties outside of their implementation within a particular layout method. There are also some key concepts which are common to all layout methods.

### Relationship to writing modes

Alignment is linked to writing modes in that when we align an item we do not consider whether we are aligning it to the physical dimensions of top, right, bottom and left. Instead we describe alignment in terms of the start and end of the particular dimension we are working with. This ensures that alignment works in the same way whichever writing mode the document has.

### Two dimensions of alignment

When using the box alignment properties you will align content on one of two axes — the inline (or main) axis, and the block (or cross) axis. The inline axis is the axis along which words in a sentence flow in the writing mode being used — for English, for example, the inline axis is horizontal. The block axis is the axis along which blocks, such as paragraph elements, are laid out and it runs across the Inline axis.

<img src="data:image/png;base64,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" width="480" height="260" />

When aligning items on the inline axis you will use the properties which begin with `justify-`:

- [`justify-items`](justify-items)
- [`justify-self`](justify-self)
- [`justify-content`](justify-content)

When aligning items on the block axis you will use the properties that begin `align-`:

- [`align-items`](align-items)
- [`align-self`](align-self)
- [`align-content`](align-content)

Flexbox adds an additional complication in that the above is true when [`flex-direction`](flex-direction) is set to `row`. The properties are swapped when flexbox is set to `column`. Therefore, when working with flexbox it is easier to think about the main and cross axis rather than inline and block. The `justify-` properties are always used to align on the main axis, the `align-` properties on the cross axis.

### The alignment subject

The **alignment subject** is the thing that is being aligned. For `justify-self` or `align-self`, or when setting these values as a group with `justify-items` or `align-items`, this will be the margin box of the element that this property is being used on. The `justify-content` and `align-content` properties differ per layout method.

### The alignment container

The **alignment container** is the box the subject is being aligned inside. This will typically be the alignment subject’s containing block. An alignment container may contain one or many alignment subjects.

The below image shows an alignment container with two alignment subjects inside.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAPgAAACqAgMAAAD9+WpkAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAJUExURf///5eXl9jY2H/w3MIAAABySURBVGje7dq7DYAwDAXAsBlDQMMIzMMKNEyJ0llAQ/gIlHuln65MYTmpv5RUNW9TcRoc/yvfvINcxHTP8mEJmXMxxsmE4ziO4ziO4ziO4/jxAv4m3xc4juM4juP4R/ipu8zd3D0Ox3Ecx3G8Nu5rYmFWGmJNiUsvb+IAAAAASUVORK5CYII=" width="248" height="170" />

### Fallback alignment

If you set an alignment that cannot be fulfilled, then the **fallback alignment** will come into play and deal with the available space. This fallback alignment is specified individually for each layout method and detailed on the page for that method.

## Types of alignment

There are three different types of alignment that the specification details; these use keyword values.

- **Positional alignment**: specifying the position of an alignment subject with relation to its alignment container.
- **Baseline alignment**: These keywords define alignment as a relationship among the baselines of multiple alignment subjects within an alignment context.
- **Distributed alignment**: These keywords define alignment as a distribution of space among alignment subjects.

### Positional alignment keyword values

The following values are defined for positional alignment, and can be used as values for content alignment with `justify-content` and `align-content` and also for self alignment with `justify-self` and `align-self`.

- `center`
- `start`
- `end`
- `self-start`
- `self-end`
- `flex-start` for Flexbox only
- `flex-end` for Flexbox only
- `left`
- `right`

Other than the physical values of `left` and `right`, which relate to physical attributes of the screen, all of the other values are logical values and relate to the writing mode of the content.

For example, when working in CSS Grid Layout, if you are working in English and set `justify-content` to `start` this will move the items in the inline dimension to the start, which will be the left as sentences in English start on the left. If you were using Arabic, a right to left language, then the same value of `start` would result in the items moving to the right, as sentences in Arabic start on the right-hand side of the page.

Both of these examples have `justify-content: start`, however the location of start changes according to the writing mode.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAd4AAABlBAMAAAARyp/yAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAwUExURcDAwJeXl////ysqSGxrfDw7VllYbZOTnKGhp7i4uXl5h66usmNjdUpJYTIxTYeHko+UcOIAAAKdSURBVHja7dxBaxNBGAbgQbbd3axJ8B9I/8LnJtGYWmhBFKyFldpjoBcPHhYiCIKwUHopCAteJAUJxEPpKRDwIkKh9CCIBHLxWMhF9BJQEEHEzcTizG5GNsWkQ/p+l5AhfHkfdmczk8OwS1OohXQ1jSgMXnin5l2YcHHv5L8EXnjhhRfe8+Flcg2GLstDF0aN/PWeugG88ML7n7xGK0VcZxyv9Vhj7/fapxReIxjDO0+htl6n11tL4X3ZnxFvnnZ8OW6dv7PkuLXGTHjtBtuJXgIx7m2e62nMW1V6n6z8SHhf7Puy1/l2N9TAa/DLZnbEuF94rk1f8rY7Km+WyG3FvctUCSXvL6INDbw5nnS+KMS1yjxXsyF5c8cqb7Nwhw7iXvfDcOykgUWFrhuevXeLezPXhLjmdZ5rbknyZq+qvD+X7F4n7q3aXln0Zikw3ODsvbV3POk9Ia5D6++jOpK9F0vK+es8+vOEF7x9tlwUvbkKs3WYv2334QAnelmXeMneTFHlzUSfT3hb7OsN0dsu6PF8zg5tV8S426O8eaV3s7LndZLepnR9n2vitbyk1361Mig/ndehKkt6++ywJHrn3NBc9zVYb9S57WZsfWUmlgtmWeG1qJpP3s8b9eHYSQODHjyjQNv90dbHuDe/pvDanuvRccy7GN02vtjAjgYK+u4Hu5W4N6NcT27T5+FcFbzuW7ovN3hNi7f09a6WEvvBUPl79GbU/nc33sBqabzfd/r4fwNeeOGFF1544YUXXnjhhRdeeOGFF1544YUXXnjhhXdk3GSN6U3XAF544YUXXnjhhRdeeOHV3Zuq/uU9dQN44YUXXnjhhRdeeOGFF1544YUXXnjhnWDhfDN44YUXXo295+18YJz/DO/MeH8D5KeBszUxuYsAAAAASUVORK5CYII=" width="478" height="101" />

### Baseline alignment

The Baseline alignment keywords are used to align the baselines of boxes across a group of alignment subjects. They can be used as values for content alignment with `justify-content` and `align-content` and also for self alignment with `justify-self` and `align-self`.

- `baseline`
- `first baseline`
- `last baseline`

Baseline content alignment — specifying a baseline alignment value for `justify-content` or `align-content` — works in layout methods that lay items out in rows. The alignment subjects are baseline aligned against each other by adding padding inside the boxes.

Baseline self alignment shifts the boxes to align by baseline by adding a margin outside the boxes. Self alignment is when using `justify-self` or `align-self`, or when setting these values as a group with `justify-items` and `align-items`.

### Distributed alignment

The **distributed alignment keywords** are used with the `align-content` and `justify-content` properties. These keywords define what happens to any additional space after alignment subjects have been displayed. The values are as follows:

- `stretch`
- `space-between`
- `space-around`
- `space-evenly`

For example, in Flex Layout items are aligned with `flex-start` initially. Working in a horizontal top to bottom writing mode such as English, with `flex-direction` as `row` the items start on the far left and any available space after displaying the items is placed after the items.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAi8AAABkAgMAAAAzujhRAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAJUExURdjY2JeXl////yIECJ4AAACVSURBVGje7dsxDkAwFAbgGtzLEQxcwr0MekpJNxSRkBTfP/5p0m/r8F5DX066AANzGTPEQjLCwMDAwMDAnGKm3Vc9SVddzHS5I5/ANCGfKmHaRVfHbbdKDQMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDcyfmeMiew/xk4n+SO26ysgIDAwMDAwPzHMZfFZgXY2ZInb9rwU8H0AAAAABJRU5ErkJggg==" width="559" height="100" />

If you set `justify-content: space-between` on the flex container, the available space is now shared out and placed between the items.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAi8AAABkAgMAAAAzujhRAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAJUExURf///5eXl9jY2H/w3MIAAACVSURBVGje7duxCYAwEEDRpHAvh9DGEZzHFSzMlNaKnkQQIrzfB16Xg0vS2E5DgoGpxvSpkToYGBgYGBiYR0y+vdVDaT5PAGHx+NAqZi7XbTHmeGyJMVMJWmFgYGBgYGBgYGBgYGBgYGBgYGBgYGBgYGBgYGBgYO4xL5fsVZhfbvxfVofxZAUGBgYGBgbmK4y/KjA/xuw6wpK8jXGKVQAAAABJRU5ErkJggg==" width="559" height="100" />

There needs to be space available in the dimension you wish to align the items in, in order for these keywords to take effect. With no space, there is nothing to distribute.

## Overflow alignment

The `safe` and `unsafe` keywords help define behavior when an alignment subject is larger than the alignment container. The `safe` keyword will align to `start` in the case of a specified alignment causing an overflow, the aim being to avoid “data loss” where part of the item is outside of the boundaries of the alignment container and can’t be scrolled to.

If you specify `unsafe` then the alignment will be honoured even if it would cause such data loss.

## Gaps between boxes

The box alignment specification also includes the `gap`, `row-gap`, and `column-gap` properties. These properties enable the setting of a consistent gap between items in a row or column, in any layout method which has items arranged in this way.

The `gap` property is a shorthand for `row-gap` and `column-gap`, which allows us to set these properties at once:

- [`row-gap`](row-gap)
- [`column-gap`](column-gap)
- [`gap`](gap)

In the below example, a grid layout uses the `gap` shorthand to set a `10px` gap between row tracks, and a `2em` gap between column tracks.

In this example I am using the [`gap`](gap) property in addition to [`gap`](gap). The gap properties were originally prefixed with `grid-` in the Grid Layout specification and some browsers only support these prefixed versions.

- [`row-gap`](row-gap)
- [`column-gap`](column-gap)
- [`gap`](gap)

The prefixed versions will be maintained as an alias of the unprefixed ones, however you can always double up in the way that you would with vendor prefixes, adding the `grid-gap` property and then the `gap` property with the same values.

Also, be aware that other things may increase the visual gap displayed, for example using the space distribution keywords or adding margins to items.

## Pages detailing individual alignment properties

As the CSS box alignment properties are implemented differently depending on the specification they interact with, refer to the following pages for each layout type for details of how to use the alignment properties with it:

- [Box alignment in Flexbox](css_box_alignment/box_alignment_in_flexbox)
- [Box alignment in CSS Grid Layout](css_box_alignment/box_alignment_in_grid_layout)
- [Box alignment in multiple-column layout](css_box_alignment/box_alignment_in_multi-column_layout)
- [Box alignment for block, absolutely positioned and table layout](css_box_alignment/box_alignment_in_block_abspos_tables)

## Reference

### CSS Properties

- [`justify-content`](justify-content)
- [`align-content`](align-content)
- [`place-content`](place-content)
- [`justify-items`](justify-items)
- [`align-items`](align-items)
- [`place-items`](place-items)
- [`justify-self`](justify-self)
- [`align-self`](align-self)
- [`place-self`](place-self)
- [`row-gap`](row-gap)
- [`column-gap`](column-gap)
- [`gap`](gap)

### Glossary Entries

- [Cross axis](https://developer.mozilla.org/en-US/docs/Glossary/Cross_Axis)
- [Main axis](https://developer.mozilla.org/en-US/docs/Glossary/Main_Axis)
- [Alignment container](https://developer.mozilla.org/en-US/docs/Glossary/Alignment_Container)
- [Alignment subject](https://developer.mozilla.org/en-US/docs/Glossary/Alignment_Subject)
- [Fallback alignment](https://developer.mozilla.org/en-US/docs/Glossary/Fallback_Alignment)

## Guides

- CSS Flexbox guide: _[Basic concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)_
- CSS Flexbox guide: _[Aligning items in a flex container](css_flexible_box_layout/aligning_items_in_a_flex_container)_
- CSS Grid guide: _[Box alignment in CSS Grid layouts](css_grid_layout/box_alignment_in_css_grid_layout)_

## External Resources

- [Box alignment cheatsheet](https://rachelandrew.co.uk/css/cheatsheets/box-alignment)
- [CSS Grid, Flexbox and Box alignment](https://www.smashingmagazine.com/2016/11/css-grids-flexbox-box-alignment-new-layout-standard/)
- [Thoughts on partial implementations of Box alignment](https://blogs.igalia.com/jfernandez/2017/05/03/can-i-use-css-box-alignment/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Alignment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Alignment</a>
