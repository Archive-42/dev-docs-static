# Stacking without the z-index property

When the [`z-index`](../../z-index) property is not specified on any element, elements are stacked in the following order (from bottom to top):

1.  The background and borders of the root element
2.  Descendant [non-positioned](../../position#static) blocks, in order of appearance in the HTML
3.  Descendant [positioned](../../position#types_of_positioning) elements, in order of appearance in the HTML

Keep in mind, when the [`order`](../../order) property alters rendering from the "order of appearance in the HTML" within [`flex`](../../flex) containers, it similarly affects the order for stacking context.

In the example below, elements \#1 through \#4 are positioned elements. Element \#5 is static, and so is drawn below the other four elements, even though it comes later in the HTML markup.

## Source code for the example

### HTML

    <div id="abs1" class="absolute">
      <b>DIV #1</b><br />position: absolute;</div>
    <div id="rel1" class="relative">
      <b>DIV #2</b><br />position: relative;</div>
    <div id="rel2" class="relative">
      <b>DIV #3</b><br />position: relative;</div>
    <div id="abs2" class="absolute">
      <b>DIV #4</b><br />position: absolute;</div>
    <div id="sta1" class="static">
      <b>DIV #5</b><br />position: static;</div>

### CSS

    b {
      font-family: sans-serif;
    }

    div {
      padding: 10px;
      border: 1px dashed;
      text-align: center;
    }

    .static {
      position: static;
      height: 80px;
      background-color: #ffc;
      border-color: #996;
    }

    .absolute {
      position: absolute;
      width: 150px;
      height: 350px;
      background-color: #fdd;
      border-color: #900;
      opacity: 0.7;
    }

    .relative {
      position: relative;
      height: 80px;
      background-color: #cfc;
      border-color: #696;
      opacity: 0.7;
    }

    #abs1 {
      top: 10px;
      left: 10px;
    }

    #rel1 {
      top: 30px;
      margin: 0px 50px 0px 50px;
    }

    #rel2 {
      top: 15px;
      left: 20px;
      margin: 0px 50px 0px 50px;
    }

    #abs2 {
      top: 10px;
      right: 10px;
    }

    #sta1 {
      background-color: #ffc;
      margin: 0px 50px 0px 50px;
    }

## See also

- [Stacking with floated blocks](stacking_and_float): How floating elements are handled with stacking.
- [Using z-index](adding_z-index): How to use `z-index` to change default stacking.
- [The stacking context](the_stacking_context): Notes on the stacking context.
- [Stacking context example 1](stacking_context_example_1): 2-level HTML hierarchy, z-index on the last level
- [Stacking context example 2](stacking_context_example_2): 2-level HTML hierarchy, z-index on all levels
- [Stacking context example 3](stacking_context_example_3): 3-level HTML hierarchy, z-index on the second level

## Original Document Information

- Author(s): Paolo Lombardi
- This article is the English translation of an article I wrote in Italian for [YappY](http://www.yappy.it). I grant the right to share all the content under the [Creative Commons: Attribution-Sharealike license](https://creativecommons.org/licenses/by-sa/2.0/).
- Last Updated Date: November 3, 2014

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/Stacking_without_z-index" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/Stacking_without_z-index</a>
