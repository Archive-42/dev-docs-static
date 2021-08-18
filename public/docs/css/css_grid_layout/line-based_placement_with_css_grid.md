# Line-based placement with CSS Grid

In the [article covering the basic concepts of grid layout](basic_concepts_of_grid_layout), we started to look at how to position items on a grid using line numbers. In this article we will fully explore how this fundamental feature of the specification works.

Starting your exploration of grid with numbered lines is the most logical place to begin, as when you use grid layout you always have numbered lines. The lines are numbered for columns and rows, and are indexed from 1. Note that grid is indexed according to the writing mode of the document. In a left to right language such as English line 1 is on the left-hand side of the grid. If you are working in a right-to-left language then line 1 will be the far right of the grid. We will learn more about the interaction between writing modes and grids in a later guide.

## A basic example

As a very simple example we can take a grid with 3 column tracks and 3 row tracks. This gives us 4 lines in each dimension.

Inside our grid container I have four child elements. If we do not place these on to the grid in any way they will lay out according to the auto-placement rules, one item in each of the first four cells. If you use the [Firefox Grid Highlighter](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Examine_grid_layouts) you can see how the grid has defined columns and rows.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA4QAAAEoCAMAAAA30c+1AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAIBUExURf9gAPirs/+DEP9IAP/TmP35/fpiQv85AP9gAP9CAP/05f/XpP//5v/esv/Zp//gonQAdP//6v1AAP+4Zv+nVnIAivbq7P/z5f/dsf//5P+uAP/Kif/65tqM6P/lsf/+5v/Hhr1H6Ps/AP+RAf+nVf+1AP///ffs7f/35f+bMdN76Nuf/f/Zpf+6a78ntP/cb/02Av/WorIAtHMAjulkhvvv7P//+vQCALMs6P+wAP+TCP+YP+RWff+jAL8yxXMAfP+bAv+5AP+hJ/+1Sf/HjvjU5//FeLxR++Bakv+qAv+rHv7k59eE5//hqv/cqP/svNxDfv/pttSM/taT/v/RftaB5+uz568g5//gbf+xALc36Lo/57kStdRRrP+JZf+tMLdD++Ndi7Ay+8FQ6P/zv/+ffK8P2OBOgP/QSv/Rrf/iteOz/tqc/fgBANiY/tmH5+rD/P+TTs1y7/sWAP+lF/Bwf/+2H/9OCfTd/O++5/p1bOSi570gtbYbzb9b/sg9uPPI5v/8zbopyv/u5d5dm//GscQusv+DPP+DWvwnANxotvjr/fxPK//Xd9+W6P+sd8li6P+1juap6O7P/f+4Gf9rKueDs/h9e96m/f/faP/HWf+5ev+/l/6Ofd2R6PxuTP+fY+Gb6P+hRPGZs/+4r9dMmm4DnP+uYmwAQH0KrP//9NeW4XsAAACgdFJOU/L+8/P+/P/z8/P///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////67kuUNAAAZl0lEQVR42uyd708byRnHSepwrSw7J5JUjmlHJA4nrbR2dwnq1kcCiY10kHZ3tXdXKelhWznZKHa1LyyDV0IBZMQvpz5ZlnCiI07hfDm4y1/ZWdsEAzY71zKNlP0+L1jJO8yMvprPzrPPMzM7cOWK5/IADAb7IHbZc+XKwGeH5cLtIZiz3ZaGLAky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" alt="Our Grid highlighted in DevTools" width="900" height="296" />

    .wrapper {
       display: grid;
       grid-template-columns: repeat(3, 1fr);
       grid-template-rows: repeat(3, 100px);
    }

    <div class="wrapper">
       <div class="box1">One</div>
       <div class="box2">Two</div>
       <div class="box3">Three</div>
       <div class="box4">Four</div>
    </div>

## Positioning items by line number

We can use line-based placement to control where these items sit on the grid. I would like the first item to start on the far left of the grid and span a single column track. It should also start on the first row line, at the top of the grid and span to the fourth row line.

    .box1 {
       grid-column-start: 1;
       grid-column-end: 2;
       grid-row-start: 1;
       grid-row-end: 4;
    }

As you position some items, other items on the grid will continue to be laid out using the auto-placement rules. We will take a proper look at how these work in a later guide but you can see as you work that grid is laying out un-placed items into empty cells of the grid.

Addressing each item individually we can place all four items spanning row and column tracks. Note that we can leave cells empty if we wish. One of the very nice things about Grid Layout is this ability to have white space in our designs without having to push things around using margins to prevent floats from rising up into the space we have left.

    <div class="wrapper">
       <div class="box1">One</div>
       <div class="box2">Two</div>
       <div class="box3">Three</div>
       <div class="box4">Four</div>
    </div>

    .box1 {
       grid-column-start: 1;
       grid-column-end: 2;
       grid-row-start: 1;
       grid-row-end: 4;
    }
    .box2 {
       grid-column-start: 3;
       grid-column-end: 4;
       grid-row-start: 1;
       grid-row-end: 3;
    }
    .box3 {
       grid-column-start: 2;
       grid-column-end: 3;
       grid-row-start: 1;
       grid-row-end: 2;
    }
    .box4 {
       grid-column-start: 2;
       grid-column-end: 4;
       grid-row-start: 3;
       grid-row-end: 4;
    }

## The `grid-column` and `grid-row` shorthands

We have quite a lot of code here to position each item. It should come as no surprise to know there is a <span class="page-not-created">shorthand</span>. The [`grid-column-start`](../grid-column-start) and [`grid-column-end`](../grid-column-end) properties can be combined into [`grid-column`](../grid-column), [`grid-row-start`](../grid-row-start) and [`grid-row-end`](../grid-row-end) into [`grid-row`](../grid-row).

    <div class="wrapper">
       <div class="box1">One</div>
       <div class="box2">Two</div>
       <div class="box3">Three</div>
       <div class="box4">Four</div>
    </div>

    .box1 {
       grid-column: 1 / 2;
       grid-row: 1 / 4;
    }
    .box2 {
       grid-column: 3 / 4;
       grid-row: 1 / 3;
    }
    .box3 {
       grid-column: 2 / 3;
       grid-row: 1 /  2;
    }
    .box4 {
       grid-column: 2 / 4;
       grid-row: 3 / 4;
    }

### Default spans

In the above examples I specified every end row and column line, in order to demonstrate the properties, however in practice if an item only spans one track you can omit the `grid-column-end` or `grid-row-end` value. Grid defaults to spanning one track. This means that our initial, long-hand, example would look like this:

    <div class="wrapper">
       <div class="box1">One</div>
       <div class="box2">Two</div>
       <div class="box3">Three</div>
       <div class="box4">Four</div>
    </div>

    .box1 {
       grid-column-start: 1;
       grid-row-start: 1;
       grid-row-end: 4;
    }
    .box2 {
       grid-column-start: 3;
       grid-row-start: 1;
       grid-row-end: 3;
    }
    .box3 {
       grid-column-start: 2;
       grid-row-start: 1;
    }
    .box4 {
       grid-column-start: 2;
       grid-column-end: 4;
       grid-row-start: 3;
    }

Our shorthand would look like the following code, with no forward slash and second value for the items spanning one track only.

    <div class="wrapper">
       <div class="box1">One</div>
       <div class="box2">Two</div>
       <div class="box3">Three</div>
       <div class="box4">Four</div>
    </div>

    .box1 {
       grid-column: 1 ;
       grid-row: 1 / 4;
    }
    .box2 {
       grid-column: 3 ;
       grid-row: 1 / 3;
    }
    .box3 {
       grid-column: 2 ;
       grid-row: 1 ;
    }
    .box4 {
       grid-column: 2 / 4;
       grid-row: 3 ;
    }

## The `grid-area` property

We can take things a step further and define each area with a single property – [`grid-area`](../grid-area). The order of the values for grid-area are as follows.

- grid-row-start
- grid-column-start
- grid-row-end
- grid-column-end

<!-- -->

    <div class="wrapper">
       <div class="box1">One</div>
       <div class="box2">Two</div>
       <div class="box3">Three</div>
       <div class="box4">Four</div>
    </div>

    .box1 {
       grid-area: 1 / 1 / 4 / 2;
    }
    .box2 {
       grid-area: 1 / 3 / 3 / 4;
    }
    .box3 {
       grid-area: 1 / 2 / 2 / 3;
    }
    .box4 {
       grid-area: 3 / 2 / 4 / 4;
    }

This order of values for `grid-area` can seem a little strange, it is the opposite of the direction in which we specify margins and padding as a shorthand for example. It may help to realize that this is due to grid using the flow-relative directions defined in the CSS Writing Modes specification. We will explore how grids work with writing modes in a later article however we have the concept of four flow-relative directions:

- block-start
- block-end
- inline-start
- inline-end

We are working in English, a left-to-right language. Our block-start is the top row line of the grid container, block-end the final row line of the container. Our inline-start is the left-hand column line as inline-start is always the point from which text would be written in the current writing mode, inline-end is the final column line of our grid.

When we specify our grid area using the `grid-area` property we first define both start lines `block-start` and `inline-start`, then both end lines `block-end` and `inline-end`. This seems unusual at first as we are used to the physical properties of top, right, bottom and left but makes more sense if you start to think of websites as being multi-directional in writing mode.

## Counting backwards

We can also count backwards from the block and inline end of the grid, for English that would be the right hand column line and final row line. These lines can be addressed as `-1`, and you can count back from there – so the penultimate line is `-2`. It is worth noting that the final line is the final line of the _explicit grid_, the grid defined by `grid-template-columns` and `grid-template-rows`, and does not take into account any rows or columns added in the _implicit grid_ outside of that.

In this next example I have flipped the layout we were working with by working from the right and bottom of our grid when placing the items.

    <div class="wrapper">
       <div class="box1">One</div>
       <div class="box2">Two</div>
       <div class="box3">Three</div>
       <div class="box4">Four</div>
    </div>

    .box1 {
       grid-column-start: -1;
       grid-column-end: -2;
       grid-row-start: -1;
       grid-row-end: -4;
    }
    .box2 {
       grid-column-start: -3;
       grid-column-end: -4;
       grid-row-start: -1;
       grid-row-end: -3;
    }
    .box3 {
       grid-column-start: -2;
       grid-column-end: -3;
       grid-row-start: -1;
       grid-row-end: -2;
    }
    .box4 {
       grid-column-start: -2;
       grid-column-end: -4;
       grid-row-start: -3;
       grid-row-end: -4;
    }

### Stretching an item across the grid

Being able to address the start and end lines of the grid is useful as you can then stretch an item right across the grid with:

    .item {
        grid-column: 1 / -1;
    }

## Gutters or Alleys

The CSS Grid Specification includes the ability to add gutters between column and row tracks with the [`column-gap`](../column-gap) and [`row-gap`](../row-gap) properties. These specify a gap that acts much like the [`column-gap`](../column-gap) property in multi-column layout.

**Note:** When grid first shipped in browsers the [`column-gap`](../column-gap), [`row-gap`](../row-gap) and [`gap`](../gap) properties were prefixed with the `grid-` prefix as `grid-column-gap`, `grid-row-gap` and `grid-gap` respectively.

Browsers are updating their rendering engines to remove this prefix, however the prefixed versions will be maintained as aliases, making them safe to use.

Gaps only appear between tracks of the grid, they do not add space to the top and bottom, left or right of the container. We can add gaps to our earlier example by using these properties on the grid container.

    <div class="wrapper">
       <div class="box1">One</div>
       <div class="box2">Two</div>
       <div class="box3">Three</div>
       <div class="box4">Four</div>
    </div>

    .box1 {
        grid-column: 1 ;
        grid-row: 1 / 4;
    }
    .box2 {
        grid-column: 3 ;
        grid-row: 1 / 3;
    }
    .box3 {
        grid-column: 2 ;
        grid-row: 1 ;
    }
    .box4 {
        grid-column: 2 / 4;
        grid-row: 3 ;
    }
    .wrapper {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(3, 100px);
        column-gap: 20px;
        row-gap: 1em;
    }

### The gap shorthand

The two properties can also be expressed as a shorthand, [`gap`](../gap). If you only give one value for `gap` it will apply to both column and row gaps. If you specify two values, the first is used for `row-gap` and the second for `column-gap`.

    .wrapper {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(3, 100px);
        gap: 1em 20px;
    }

In terms of line-based positioning of items, the gap acts as if the line has gained extra width. Anything starting at that line starts after the gap and you cannot address the gap or place anything into it. If you want gutters that act more like regular tracks you can of course define a track for the purpose instead.

## Using the `span` keyword

In addition to specifying the start and end lines by number, you can specify a start line and then the number of tracks you would like the area to span.

    <div class="wrapper">
       <div class="box1">One</div>
       <div class="box2">Two</div>
       <div class="box3">Three</div>
       <div class="box4">Four</div>
    </div>

    .box1 {
        grid-column: 1;
        grid-row: 1 / span 3;
    }
    .box2 {
        grid-column: 3;
        grid-row: 1 / span 2;
    }
    .box3 {
        grid-column: 2;
        grid-row: 1;
    }
    .box4 {
        grid-column: 2 / span 2;
        grid-row: 3;
    }

You can also use the `span` keyword in the value of `grid-row-start`/`grid-row-end` and `grid-column-start/grid-column-end`. The following two examples will create the same grid area. In the first we set the start row line, then the end line we explain that we want to span 3 lines. The area will start at line 1 and span 3 lines to line 4.

    .box1 {
        grid-column-start: 1;
        grid-row-start: 1;
        grid-row-end: span 3;
    }

In the second example, we specify the end row line we want the item to finish at and then set the start line as `span 3`. This means the item will need to span upwards from the specified row line. The area will start at line 4 and span 3 lines to line 1.

    .box1 {
        grid-column-start: 1;
        grid-row-start: span 3;
        grid-row-end: 4;
    }

To become familiar with line based positioning in grid try to build a few common layouts by placing items onto grids with varying numbers of columns. Remember that if you do not place all of the items, any leftover items will be placed according to auto-placement rules. This may result in the layout you want, but if something is appearing somewhere unexpected, check that you have set a position for it.

Also, remember that items on the grid can overlap each other when you place them explicitly like this. That can create some nice effects, however you can also end up with things overlapping incorrectly if you specify the wrong start or end line. The [Firefox Grid Highlighter](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Examine_grid_layouts) can be very useful as you learn, especially if your grid is quite complicated.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid</a>
