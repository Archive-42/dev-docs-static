# Box alignment in CSS Grid Layout

CSS Grid Layout implements the specification [Box Alignment Level 3](https://drafts.csswg.org/css-align/) which is the same standard [flexbox](../css_flexible_box_layout) uses for aligning items in its flex container. This specification details how alignment should work in all the different layout methods. Layout methods will conform to the specification where possible and implement individual behavior based on their differences (features and constraints). While the specification currently specifies alignment details for all layout methods, browsers have not fully implemented all of the specification; however, the CSS Grid Layout method has been widely adopted.

This guide presents demonstrations of how box alignment in grid layout works. You will see many similarities in how these properties and values work in flexbox. Due to grid being two-dimensional and flexbox one-dimensional there are some small differences that you should watch out for. So we will start by looking at the two axes that we deal with when aligning things in a grid.

## The two axes of a grid layout

When working with grid layout you have two axes available to align things against – the _block axis_ and the _inline axis_. The block axis is the axis upon which blocks are laid out in block layout. If you have two paragraphs on your page they display one below the other, so it is this direction we describe as the block axis.

<img src="data:image/png;base64,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" width="940" height="306" />

The _inline axis_ runs across the block axis, it is the direction in which text in regular inline flow runs.

<img src="data:image/png;base64,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" width="940" height="306" />

We are able to align the content inside grid areas, and the grid tracks themselves on these two axes.

## Aligning items on the Block Axis

The [`align-self`](../align-self) and [`align-items`](../align-items) properties control alignment on the block axis. When we use these properties, we are changing the alignment of the item within the grid area you have placed it.

In the following example, I have four grid areas within my grid. I can use the [`align-items`](../align-items) property on the grid container, to align the items using one of the following values:

- `auto`
- `normal`
- `start`
- `end`
- `center`
- `stretch`
- `baseline`
- `first baseline`
- `last baseline`

<!-- -->

    .wrapper {
      display: grid;
      grid-template-columns: repeat(8, 1fr);
      gap: 10px;
      grid-auto-rows: 100px;
      grid-template-areas:
        "a a a a b b b b"
        "a a a a b b b b"
        "c c c c d d d d"
        "c c c c d d d d";
      align-items: start;
    }
    .item1 {
      grid-area: a;
    }
    .item2 {
      grid-area: b;
    }
    .item3 {
      grid-area: c;
    }
    .item4 {
      grid-area: d;
    }

    <div class="wrapper">
      <div class="item1">Item 1</div>
      <div class="item2">Item 2</div>
      <div class="item3">Item 3</div>
      <div class="item4">Item 4</div>
    </div>

Keep in mind that once you set `align-items: start`, the height of each child `<div>` will be determined by the contents of the `<div>`. This is in contrast to omitting `align-items` completely, in which case the height of each `<div>` stretches to fill its grid area.

The [`align-items`](../align-items) property sets the [`align-self`](../align-self) property for all of the child grid items. This means that you can set the property individually, by using `align-self` on a grid item.

In this next example, I am using the `align-self` property, to demonstrate the different alignment values. The first area, is showing the default behavior of `align-self`, which is to stretch. The second item, has an `align-self` value of `start`, the third `end` and the fourth `center`.

    .wrapper {
      display: grid;
      grid-template-columns: repeat(8, 1fr);
      gap: 10px;
      grid-auto-rows: 100px;
      grid-template-areas:
        "a a a a b b b b"
        "a a a a b b b b"
        "c c c c d d d d"
        "c c c c d d d d";
    }
    .item1 {
      grid-area: a;
    }
    .item2 {
      grid-area: b;
      align-self: start;
    }
    .item3 {
      grid-area: c;
      align-self: end;
    }
    .item4 {
      grid-area: d;
      align-self: center;
    }

    <div class="wrapper">
      <div class="item1">Item 1</div>
      <div class="item2">Item 2</div>
      <div class="item3">Item 3</div>
      <div class="item4">Item 4</div>
    </div>

### Items with an intrinsic aspect ratio

The specification details that the default behavior in [`align-self`](../align-self) is to stretch, except for items which have an intrinsic aspect ratio, in this case they behave as `start`. The reason for this, is that if items with an aspect ratio are set to stretch, this default would distort them.

This behavior has now been clarified in the specification, with browsers yet to implement the correct behavior. Until that happens, you can ensure that items do not stretch, such as images, which are direct children of the grid, by setting [`align-self`](../align-self) and [`justify-self`](../justify-self) to start. This will mimic the correct behavior once implemented.

## Justifying Items on the Inline Axis

As [`align-items`](../align-items) and [`align-self`](../align-self) deal with the alignment of items on the block axis, [`justify-items`](../justify-items) and [`justify-self`](../justify-self) do the same job on the inline axis. The values you can choose from are the same as for `align-self`.

- `auto`
- `normal`
- `start`
- `end`
- `center`
- `stretch`
- `baseline`
- `first baseline`
- `last baseline`

You can see the same example as used for [`align-items`](../align-items), below. This time we are applying the [`justify-self`](../justify-self) property.

Once again the default is `stretch`, other than for items with an intrinsic aspect ratio. This means that by default, grid items will cover their grid area, unless you change that by setting alignment. The first item in the example demonstrates this default alignment:

    .wrapper {
      display: grid;
      grid-template-columns: repeat(8, 1fr);
      gap: 10px;
      grid-auto-rows: 100px;
      grid-template-areas:
        "a a a a b b b b"
        "a a a a b b b b"
        "c c c c d d d d"
        "c c c c d d d d";
    }
    .item1 {
      grid-area: a;
    }
    .item2 {
      grid-area: b;
      justify-self: start;
    }
    .item3 {
      grid-area: c;
      justify-self: end;
    }
    .item4 {
      grid-area: d;
      justify-self: center;
    }

    <div class="wrapper">
      <div class="item1">Item 1</div>
      <div class="item2">Item 2</div>
      <div class="item3">Item 3</div>
      <div class="item4">Item 4</div>
    </div>

As with [`align-self`](../align-self) and [`align-items`](../align-items), you can apply [`justify-items`](../justify-items) to the grid container, to set the [`justify-self`](../justify-self) value for all items.

The [`justify-self`](../justify-self) and [`justify-items`](../justify-items) properties are not implemented in flexbox. This is due to the one-dimensional nature of [flexbox](../css_flexible_box_layout), and that there may be multiple items along the axis, making it impossible to justify a single item. To align items along the main, inline axis in flexbox you use the [`justify-content`](../justify-content) property.

### Shorthand properties

The [`place-items`](../place-items) property is shorthand for [`align-items`](../align-items) and [`justify-items`](../justify-items).

The [`place-self`](../place-self) property is shorthand for [`align-self`](../align-self) and [`justify-self`](../justify-self).

## Center an item in the area

By combining the align and justify properties we can easily center an item inside a grid area.

    .wrapper {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
      grid-auto-rows: 200px;
      grid-template-areas:
        ". a a ."
        ". a a .";
    }
    .item1 {
      grid-area: a;
      align-self: center;
      justify-self: center;
    }

    <div class="wrapper">
     <div class="item1">Item 1</div>
    </div>

## Aligning the grid tracks on the block axis

If you have a situation where your grid tracks use an area that is smaller than the grid container, then you can align the grid tracks themselves, inside that container. Once again, this operates on the block and inline axes, with [`align-content`](../align-content) aligning tracks on the block axis, and [`justify-content`](../justify-content) performing alignment on the inline axis. The [`place-content`](../place-content) property is shorthand for [`align-content`](../align-content) and [`justify-content`](../justify-content). The values for [`align-content`](../align-content), [`justify-content`](../justify-content) and [`place-content`](../place-content) are:

- `normal`
- `start`
- `end`
- `center`
- `stretch`
- `space-around`
- `space-between`
- `space-evenly`
- `baseline`
- `first baseline`
- `last baseline`

In the below example I have a grid container of 500 pixels by 500 pixels. I have defined 3 row and column tracks each of 100 pixels with a 10 pixel gutter. This means that there is space inside the grid container both in the block and inline directions.

The `align-content` property is applied to the grid container as it works on the entire grid. The default behavior in grid layout is `start`, which is why our grid tracks are in the top left corner of the grid, aligned against the start grid lines:

    .wrapper {
      display: grid;
      grid-template-columns: repeat(3, 100px);
      grid-template-rows: repeat(3, 100px);
      height: 500px;
      width: 500px;
      gap: 10px;
      grid-template-areas:
        "a a b"
        "a a b"
        "c d d";
    }
    .item1 {
      grid-area: a;
    }
    .item2 {
      grid-area: b;
    }
    .item3 {
      grid-area: c;
    }
    .item4 {
      grid-area: d;
    }

    <div class="wrapper">
      <div class="item1">Item 1</div>
      <div class="item2">Item 2</div>
      <div class="item3">Item 3</div>
      <div class="item4">Item 4</div>
    </div>

If I add `align-content` to my container, with a value of `end`, the tracks all move to the end line of the grid container in the block dimension:

    .wrapper {
      display: grid;
      grid-template-columns: repeat(3, 100px);
      grid-template-rows: repeat(3, 100px);
      height: 500px;
      width: 500px;
      gap: 10px;
      grid-template-areas:
        "a a b"
        "a a b"
        "c d d";
      align-content: end;
    }
    .item1 {
      grid-area: a;
    }
    .item2 {
      grid-area: b;
    }
    .item3 {
      grid-area: c;
    }
    .item4 {
      grid-area: d;
    }

    <div class="wrapper">
      <div class="item1">Item 1</div>
      <div class="item2">Item 2</div>
      <div class="item3">Item 3</div>
      <div class="item4">Item 4</div>
    </div>

We can also use values for this property that you may be familiar with from flexbox; the space distribution values of `space-between`, `space-around` and `space-evenly`. If we update [`align-content`](../align-content) to `space-between`, you can see how the elements on our grid space out:

    .wrapper {
      display: grid;
      grid-template-columns: repeat(3, 100px);
      grid-template-rows: repeat(3, 100px);
      height: 500px;
      width: 500px;
      gap: 10px;
      grid-template-areas:
        "a a b"
        "a a b"
        "c d d";
      align-content: space-between;
    }
    .item1 {
      grid-area: a;
    }
    .item2 {
      grid-area: b;
    }
    .item3 {
      grid-area: c;
    }
    .item4 {
      grid-area: d;
    }

    <div class="wrapper">
      <div class="item1">Item 1</div>
      <div class="item2">Item 2</div>
      <div class="item3">Item 3</div>
      <div class="item4">Item 4</div>
    </div>

It is worth noting, that using these space distribution values may cause items on your grid to become larger. If an item spans more than one grid track, as further space is added between the tracks, that item needs to become large to absorb the space. We’re always working in a strict grid. Therefore, if you decide to use these values, ensure that the content of your tracks can cope with the extra space, or that you have used alignment properties on the items, to cause them to move to the start rather than stretch.

In the below image I have placed the grid with `align-content`, with a value of `start` alongside the grid when `align-content` has a value of `space-between`. You can see how items 1 and 2, which span two row tracks have taken on extra height as they gain the additional space added to the gap between those two tracks:

<img src="data:image/png;base64,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coGNtdabL1+gCOCGIr6876+vb6wS1q/hnz3avx003P77h2wAisifIt711/uHny7/frUieN1+dg3d16+erLe/X73uPlsu9Ijud/fbABSRQ0W01vufj19svlgRbG6+Hj3P4PPeU/a2ubn3+fly4ff+eut+G4AicqiItfXD48u99stVwfGHt5/f/RTj3fs/Pjxlb+29D7+9T462FHjeW1+73wagiBwqYm3t04u9ncaqwGkeXx7/9GbeYvvy2HnKw9WPL9tLRvqz9Y0HbGADisidItY2Ll+0/frKwNl6+9evv0QNvvl5b/Nj4ymP1vj4514qsSUh/aHZABSRP0Wsbbx68bKxOqQ3t//47+8x6f/59be3O87TSmzz9c8rZwNQRO4UAdJhA7AB2ABIhw3ABmADIB02ABuADYB02ABsADYA0mEDsAHYAEiHDcAGYAMgHTYAG4ANgHTYAGwANgDSYQOwAdgASIcNwAZgAyAdNgAbgA2AdNgAbAA2ANJhA7AB2ABIhw1AEbCBuBXf990H2nUfzPh3kv5wb47fcL62ubzYABSx4opYQLp7MhwOj3que0/nbnd64i8h6dtj3tuu4955SXC2rwYXR7subACKyI8iFpBObQeTXr3R7d55ZtzxIDhYRtLru9PgrFt329t39daYToYXwVndgQ1AEblRxALSm42X+2e+vzM79ep1mjE5fMLn8JlTOnvqtjrLSbrfCo48v32+6/PZIG+84brUoxP31mifdUdbg07PhQ1AEblRxKKVYKNNpG/1g6NT32mNW3XX6R7ujsddtzXuxalee395SR+1B51xz6eWDhuO0+51xyfNsD/ee+vEq4+mwSlsAIrIjyLuJL09CIYHznQ47Qyb44vJbBDMprP9SeyJjWUl3eGkty46w5OPs6N+56g53T+n3oazQec8nBby9a837XRhA1BEfhRxJ+neVac3ujrv1vvBSX0wOSU/PBglEz9/mb3f8/rnTa8/bG4Ngl57/7zrDIKT0f86c793ti6Ovq65XNkAFJFDG/CJdH8wmU77gxNvcO57n4LTdOK31N7vuUT6x/3ZdDqb9Xb2uQgmu96nhHR/Omw6sAEoIj+KuJd052Lo1Zu+7w7IK6+Rvtzez0l/2Tnw+D2hrf3hDdK98dmu6+KbAigiP4q4l3RvMHlGp2V8m/RV8P6h73rtk1uk+62zZyOvtw0b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" alt="Demonstrating how items become larger if we use space-between." width="1030" height="534" />

## Justifying the grid tracks on the inline axis

On the inline axis, we can use [`justify-content`](../justify-content) to perform the same type of alignment that we used [`align-content`](../align-content) for in the block axis.

Using the same example, I am setting [`justify-content`](../justify-content) to `space-around`. This once again causes tracks which span more than one column track to gain extra space:

    .wrapper {
      display: grid;
      grid-template-columns: repeat(3, 100px);
      grid-template-rows: repeat(3, 100px);
      height: 500px;
      width: 500px;
      gap: 10px;
      grid-template-areas:
        "a a b"
        "a a b"
        "c d d";
      align-content: space-between;
      justify-content: space-around;
    }
    .item1 {
      grid-area: a;
    }
    .item2 {
      grid-area: b;
    }
    .item3 {
      grid-area: c;
    }
    .item4 {
      grid-area: d;
    }

    <div class="wrapper">
      <div class="item1">Item 1</div>
      <div class="item2">Item 2</div>
      <div class="item3">Item 3</div>
      <div class="item4">Item 4</div>
    </div>

## Alignment and auto margins

Another way to align items inside their area, is to use auto margins. If you have ever centered your layout in the viewport, by setting the right and left margin of the container block to `auto`, you know that an auto margin absorbs all of the available space. By setting the margin to `auto` on both sides, it pushes the block into the middle as both margins attempt to take all of the space.

In this next example, I have given item 1 a left margin of `auto`. You can see how the content is now pushed over to the right side of the area, as the auto margin takes up remaining space, after room for the content of that item has been assigned:

    .wrapper {
      display: grid;
      grid-template-columns: repeat(3, 100px);
      grid-template-rows: repeat(3, 100px);
      height: 500px;
      width: 500px;
      gap: 10px;
      grid-template-areas:
        "a a b"
        "a a b"
        "c d d";
    }
    .item1 {
      grid-area: a;
      margin-left: auto;
    }
    .item2 {
      grid-area: b;
    }
    .item3 {
      grid-area: c;
    }
    .item4 {
      grid-area: d;
    }

    <div class="wrapper">
      <div class="item1">Item 1</div>
      <div class="item2">Item 2</div>
      <div class="item3">Item 3</div>
      <div class="item4">Item 4</div>
    </div>

You can see how the item is aligned by using the [Firefox Grid Highlighter](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Examine_grid_layouts):

<img src="data:image/png;base64,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" alt="Image showing auto-margins using the Grid Highlighter." width="1000" height="1000" />

## Alignment and Writing Modes

In all of these examples I have been working in English, which is a left-to-right language. This means that our start lines are top and left of our grid when thinking in physical directions.

CSS Grid Layout, and the Box Alignment specification are designed to work with writing modes in CSS. This means that if you are working in a right to left language, such as Arabic, the start of the grid would be the top and right, so the default of `justify-content: start` would be for grid tracks to start on the right hand side of the grid.

Setting auto margins, using `margin-right` or `margin-left` however, or absolutely positioning items using the `top`, `right`, `bottom` and `left` offsets would not honor writing modes. In the next guide, we will look further into this interaction between CSS grid layout, box alignment and writing modes. This will be important to understand, if you develop sites that are then displayed in multiple languages, or if you want to mix languages or writing modes in a design.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Box_Alignment_in_CSS_Grid_Layout" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Box_Alignment_in_CSS_Grid_Layout</a>
