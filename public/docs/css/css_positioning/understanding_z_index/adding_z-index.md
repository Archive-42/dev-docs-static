# Using z-index

The first part of this article, [Stacking without the z-index property](stacking_without_z-index), explains how stacking is arranged by default. If you want to create a custom stacking order, you can use the [`z-index`](../../z-index) property on a [positioned](../../position#types_of_positioning) element.

The `z-index` property can be specified with an integer value (positive, zero, or negative), which represents the position of the element along the z-axis. If you are not familiar with the z-axis, imagine the page as a stack of layers, each one having a number. Layers are rendered in numerical order, with larger numbers above smaller numbers.

- bottom layer _(farthest from the observer)_
- ...
- Layer -3
- Layer -2
- Layer -1
- Layer 0 _(default rendering layer)_
- Layer 1
- Layer 2
- Layer 3
- ...
- top layer _(closest to the observer)_

**Notes:**

- When no `z-index` property is specified, elements are rendered on the default rendering layer 0 (zero).
- If several elements share the same `z-index` value (i.e., they are placed on the same layer), stacking rules explained in the section [Stacking without the z-index property](stacking_without_z-index) apply.

In the following example, the layers' stacking order is rearranged using `z-index`. The `z-index` of element \#5 has no effect since it is not a positioned element.

## Source code for the example

### HTML

    <div id="abs1">
      <b>DIV #1</b>
      <br />position: absolute;
      <br />z-index: 5;
    </div>

    <div id="rel1">
      <b>DIV #2</b>
      <br />position: relative;
      <br />z-index: 3;
    </div>

    <div id="rel2">
      <b>DIV #3</b>
      <br />position: relative;
      <br />z-index: 2;
    </div>

    <div id="abs2">
      <b>DIV #4</b>
      <br />position: absolute;
      <br />z-index: 1;
    </div>

    <div id="sta1">
      <b>DIV #5</b>
      <br />no positioning
      <br />z-index: 8;
    </div>

### CSS

    div {
      padding: 10px;
      opacity: 0.7;
      text-align: center;
    }

    b {
      font-family: sans-serif;
    }

    #abs1 {
      z-index: 5;
      position: absolute;
      width: 150px;
      height: 350px;
      top: 10px;
      left: 10px;
      border: 1px dashed #900;
      background-color: #fdd;
    }

    #rel1 {
      z-index: 3;
      height: 100px;
      position: relative;
      top: 30px;
      border: 1px dashed #696;
      background-color: #cfc;
      margin: 0px 50px 0px 50px;
    }

    #rel2 {
      z-index: 2;
      height: 100px;
      position: relative;
      top: 15px;
      left: 20px;
      border: 1px dashed #696;
      background-color: #cfc;
      margin: 0px 50px 0px 50px;
    }

    #abs2 {
      z-index: 1;
      position: absolute;
      width: 150px;
      height: 350px;
      top: 10px;
      right: 10px;
      border: 1px dashed #900;
      background-color: #fdd;
    }

    #sta1 {
      z-index: 8;
      height: 70px;
      border: 1px dashed #996;
      background-color: #ffc;
      margin: 0px 50px 0px 50px;
    }

## See also

- [Stacking without the z-index property](stacking_without_z-index): The stacking rules that apply when `z-index` is not used.
- [Stacking with floated blocks](stacking_and_float): How floating elements are handled with stacking.
- [The stacking context](the_stacking_context): Notes on the stacking context.
- [Stacking context example 1](stacking_context_example_1): 2-level HTML hierarchy, z-index on the last level
- [Stacking context example 2](stacking_context_example_2): 2-level HTML hierarchy, z-index on all levels
- [Stacking context example 3](stacking_context_example_3): 3-level HTML hierarchy, z-index on the second level

## Original Document Information

- Author(s): Paolo Lombardi
- This article is the English translation of an article I wrote in Italian for [YappY](http://www.yappy.it). I grant the right to share all the content under the [Creative Commons: Attribution-Sharealike license](https://creativecommons.org/licenses/by-sa/2.0/).
- Last Updated Date: November 3, 2014

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/Adding_z-index" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/Adding_z-index</a>
