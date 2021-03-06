# Stacking context example 1

« [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) « [Understanding CSS z-index](../understanding_z_index)

## Stacking context example 1

Let's start with a basic example. In the root stacking context we have two DIVs (DIV \#1 and DIV \#3), both relatively positioned, but without z-index properties. Inside DIV \#1 there is an absolutely positioned DIV \#2, while in DIV \#3 there is an absolutely positioned DIV \#4, both without z-index properties.

The only stacking context is the root context. Without z-indexes, elements are stacked in order of occurrence.

<img src="data:image/png;base64,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" alt="Stacking context example 1" class="internal" width="352" height="254" />

If DIV \#2 is assigned a positive (non-zero and non-auto) z-index value, it is rendered above all the other DIVs.

<img src="data:image/png;base64,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" alt="Stacking context example 1" class="internal" width="354" height="255" />

Then if DIV \#4 is also assigned a positive z-index greater than DIV \#2's z-index, it is rendered above all the other DIVs including DIV \#2.

<img src="data:image/png;base64,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" alt="Stacking context example 1" class="internal" width="353" height="257" />

In this last example you can see that DIV \#2 and DIV \#4 are not siblings, because they belong to different parents in the HTML elements' hierarchy. Even so, stacking of DIV \#4 with respect of DIV \#2 can be controlled through z-index. It happens that, since DIV \#1 and DIV \#3 are not assigned any z-index value, they do not create a stacking context. This means that all their content, including DIV \#2 and DIV \#4, belongs to the same root stacking context.

In terms of stacking contexts, DIV \#1 and DIV \#3 are assimilated into the root element, and the resulting hierarchy is the following:

- root stacking context
  - DIV \#2 (z-index 1)
  - DIV \#4 (z-index 2)

**Note:** DIV \#1 and DIV \#3 are not translucent. It is important to remember that assigning an opacity less than 1 to a positioned element implicitly creates a stacking context, just like adding a z-index value. And this example shows what happens when a parent element does not create a stacking context.

## Example

### HTML

    <div id="div1">
    <br /><span class="bold">DIV #1</span>
    <br />position: relative;
       <div id="div2">
       <br /><span class="bold">DIV #2</span>
       <br />position: absolute;
       <br />z-index: 1;
       </div>
    </div>

    <br />

    <div id="div3">
    <br /><span class="bold">DIV #3</span>
    <br />position: relative;
       <div id="div4">
       <br /><span class="bold">DIV #4</span>
       <br />position: absolute;
       <br />z-index: 2;
       </div>
    </div>

    </body></html>

### CSS

    .bold {
        font-weight: bold;
        font: 12px Arial;
    }
    #div1,
    #div3 {
        height: 80px;
        position: relative;
        border: 1px dashed #669966;
        background-color: #ccffcc;
        padding-left: 5px;
    }
    #div2 {
        opacity: 0.8;
        z-index: 1;
        position: absolute;
        width: 150px;
        height: 200px;
        top: 20px;
        left: 170px;
        border: 1px dashed #990000;
        background-color: #ffdddd;
        text-align: center;
    }
    #div4 {
        opacity: 0.8;
        z-index: 2;
        position: absolute;
        width: 200px;
        height: 70px;
        top: 65px;
        left: 50px;
        border: 1px dashed #000099;
        background-color: #ddddff;
        text-align: left;
        padding-left: 10px;
    }

### Result

## See also

- [Stacking without the z-index property](stacking_without_z-index): The stacking rules that apply when `z-index` is not used.
- [Stacking with floated blocks](stacking_and_float): How floating elements are handled with stacking.
- [Using z-index](adding_z-index): How to use `z-index` to change default stacking.
- [The stacking context](the_stacking_context): Notes on the stacking context.
- [Stacking context example 2](stacking_context_example_2): 2-level HTML hierarchy, `z-index` on all levels
- [Stacking context example 3](stacking_context_example_3): 3-level HTML hierarchy, `z-index` on the second level

## Original Document Information

- Author(s): Paolo Lombardi
- This article is the English translation of an article I wrote in Italian for [YappY](http://www.yappy.it). I grant the right to share all the content under the [Creative Commons: Attribution-Sharealike license](https://creativecommons.org/licenses/by-sa/2.0/).
- Last Updated Date: July 9, 2005

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/Stacking_context_example_1" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/Stacking_context_example_1</a>
