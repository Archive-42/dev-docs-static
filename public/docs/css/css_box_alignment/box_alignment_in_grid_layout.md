# Box alignment in grid layout

The [Box Alignment](../css_box_alignment) specification details how alignment works in various layout methods. On this page we explore how box alignment works in the context of [CSS Grid Layout](../css_grid_layout).

As this page aims to detail things which are specific to CSS Grid Layout and Box Alignment, it should be read in conjunction with the main [Box Alignment](../css_box_alignment) page which details the common features of box alignment across layout methods.

## Basic Example

In this example using grid layout, there is extra space in the grid container after laying out the fixed width tracks on the inline (main) axis. This space is distributed using `justify-content`. On the block (cross) axis the alignment of the items inside their grid areas is controlled with `align-items`. The first item overrides the `align-items` value set on the group by setting `align-self` to `center`.

## Grid axes

As a two-dimensional layout method, when working with grid layout we always have two axes on which to align our items. We have access to all of the box alignment properties to help us achieve this.

The inline axis is the axis that corresponds to the direction that words in a sentence would run in the writing mode used. Therefore, in a horizontal language such as English or Arabic the inline direction runs horizontally. Should you be in a vertical writing mode the inline axis will run vertically.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA6wAAAEyCAMAAADJFq1sAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAB+UExURf/05v/hxv/z4//ny//nyf/x3////5eXl//RuP/158u/ssvGv//hxf/ozcu+sP/36f/Guf/KvczGvebd0wAAAOXTv//u4//QxP/r2f/Yxv/i1//o3v/y4//e0v/VzRsaGFlVUDo3NLuyqN7UyPXq3HlzbKSck42Gfv/58eXCrzjMrZQAAAxaSURBVHja7N1td9o2GIBhYUxSpXVlER9ZfuU96f7/H9wj2STQkjZNFuAs93W2gBzYB4W7sgzp1I1ovgC4as3Njbq5+VExE8C1q35IrNWXqvGTbxMAV+nbxDeSqbrxXyrjUwBXzJvqi7qRs2GfZjMAVytLfRNjlVaVBnC9pNYY6ySdaQXgaulZOomxfiNW4Npj/UasALECIFaAWAEQKwBiBYgVALECIFaAWAEQKwBiBYgVALECeG2sWh/fvvBtABdfWdvxpj2ZZauoFbiKWHVVOh0eUfYnqtTJycMALhGrHWK1p2O1xApcY6zh72savuq4X9UqHNYHh0kXuNSeVWI1WptWqtTa17WTHn3dyFZVJzIMh8exbxLfsIUFLrey1o2IVXZ5npdOVXLTh21sHu7oNo5bVZZyoCNW4FIraz7qjc97523flnVT5k5XeReGppNb+deUee/7hliBS62seVeLTmKdhLuldc7IYupaWw571tLK92VQxhNmZhO47J51ZkOscqZb9W5WlTZ34Ui8GlzacLiT02BSBS66Z91fDZbz3cYYo1pZQuvcJbKYmmFldXI47Fm5ugRcdmXdx+pzW/uubGwvO9laToV7X8eGy9pXEi2xAtexsmpd23jdt5LT4dwOV4XzXsdb22lOg4GLxjob3zptpFk9894p3frGhXdUtfMy1joe1rqZMZPABU+D9x9K2n9mSevnjyod3vILOMCFYwVArACIFSBWAMQKgFgBYgVArACIFSBWAMQKgFgBYgVArACxEitArACIFSBWAMQKgFgBYgVArACIFSBWAMQKgFgBYgVArACIFSBWAMQKECuxXpNlsTwcLoq5ejg+9Kvborj96VB4HogVH/lzOY5Vx1gXf4h1VRSrnw8tiJVYcfaV9U8/n02xWhSbX37C/FiJFR+/si5X291i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" width="940" height="306" />

To align things on the inline axis you use the properties that start with `justify-`, [`justify-content`](../justify-content), [`justify-items`](../justify-items) and [`justify-self`](../justify-self).

The block axis crosses the inline axis in the direction that blocks are displayed down the page ??? for example paragraphs in English are displayed one below the other vertically. This, therefore is the block dimension.

To align things on the block axis you use the properties that start with `align-`, [`align-content`](../align-content), [`align-items`](../align-items) and [`align-self`](../align-self).

<img src="data:image/png;base64,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" width="940" height="306" />

## Self alignment

- [`justify-self`](../justify-self)
- [`align-self`](../align-self)
- [`place-self`](../place-self)
- [`justify-items`](../justify-items)
- [`align-items`](../align-items)
- [`place-items`](../place-items)

These properties deal with aligning the item inside the grid area it is placed into. The properties `align-items` and `justify-items` are applied to the grid container and set the `align-self` and `justify-self` properties as a group. This means that you can set alignment for all of your grid Items at once, then override any items that need a different alignment by applying the `align-self` or `justify-self` property to the rules for the individual grid Items.

The initial value for `align-self` and `justify-self` is `stretch` so the item will stretch over the entire grid area. The exception to this rule is where the item has an intrinsic aspect ratio, for example an image. In this case the item will be aligned to `start` in both dimensions in order that the image is not distorted.

## Content alignment

- [`justify-content`](../justify-content)
- [`align-content`](../align-content)
- [`place-content`](../place-content)

These properties deal with aligning the tracks of the grid when there is extra space to distribute. This scenario will occur if the tracks that you have defined total less than the total width of the grid container.

## Gap and legacy grid-gap properties

- [`row-gap`](../row-gap)
- [`column-gap`](../column-gap)
- [`gap`](../gap)

The Grid specification originally contained the definition for the properties [`row-gap`](../row-gap), [`column-gap`](../column-gap) and [`gap`](../gap). These have since been moved into the Box Alignment specification and renamed to [`row-gap`](../row-gap), [`column-gap`](../column-gap), and [`gap`](../gap). This allows them to be used for other layout methods where a gap between items makes sense.

The updated properties have not yet been implemented in all browsers. Therefore, to use the gap properties in grid layout, you should use the `grid-row-gap`, `grid-column-gap` and `grid-gap` versions to ensure full compatibility. You could double up the properties and use both as you would for vendor prefixes.

## Reference

### CSS Properties

- [`justify-content`](../justify-content)
- [`align-content`](../align-content)
- [`place-content`](../place-content)
- [`justify-items`](../justify-items)
- [`align-items`](../align-items)
- [`place-items`](../place-items)
- [`justify-self`](../justify-self)
- [`align-self`](../align-self)
- [`place-self`](../place-self)
- [`row-gap`](../row-gap)
- [`column-gap`](../column-gap)
- [`gap`](../gap)

### Glossary Entries

- [Cross Axis](https://developer.mozilla.org/en-US/docs/Glossary/Cross_Axis)
- [Main Axis](https://developer.mozilla.org/en-US/docs/Glossary/Main_Axis)

## Guides

- [Alignment in grid layout](../css_grid_layout/box_alignment_in_css_grid_layout)

## External Resources

- [Box alignment cheatsheet](https://rachelandrew.co.uk/css/cheatsheets/box-alignment)
- [CSS Grid, Flexbox and Box Alignment](https://www.smashingmagazine.com/2016/11/css-grids-flexbox-box-alignment-new-layout-standard/)
- [Thoughts on partial implementations of Box Alignment](https://blogs.igalia.com/jfernandez/2017/05/03/can-i-use-css-box-alignment/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Alignment/Box_Alignment_In_Grid_Layout" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Alignment/Box_Alignment_In_Grid_Layout</a>
