# The stacking context

The **stacking context** is a three-dimensional conceptualization of HTML elements along an imaginary z-axis relative to the user, who is assumed to be facing the viewport or the webpage. HTML elements occupy this space in priority order based on element attributes.

## The stacking context

In the previous part of this article, [Using z-index](adding_z-index), the rendering order of certain elements is influenced by their `z-index` value. This occurs because these elements have special properties which cause them to form a _stacking context_.

A stacking context is formed, anywhere in the document, by any element in the following scenarios:

- Root element of the document (`<html>`).
- Element with a [`position`](../../position) value `absolute` or `relative` and [`z-index`](../../z-index) value other than `auto`.
- Element with a [`position`](../../position) value `fixed` or `sticky` (sticky for all mobile browsers, but not older desktop).
- Element that is a child of a [flex](../../css_flexible_box_layout/basic_concepts_of_flexbox) container, with [`z-index`](../../z-index) value other than `auto`.
- Element that is a child of a [`grid`](../../grid) container, with [`z-index`](../../z-index) value other than `auto`.
- Element with a [`opacity`](../../opacity) value less than `1` (See [the specification for opacity](https://www.w3.org/TR/css3-color/#transparency)).
- Element with a [`mix-blend-mode`](../../mix-blend-mode) value other than `normal`.
- Element with any of the following properties with value other than `none`:
  - [`transform`](../../transform)
  - [`filter`](../../filter)
  - [`perspective`](../../perspective)
  - [`clip-path`](../../clip-path)
  - [`mask`](../../mask) / [`mask-image`](../../mask-image) / [`mask-border`](../../mask-border)
- Element with a [`isolation`](../../isolation) value `isolate`.
- Element with a [`-webkit-overflow-scrolling`](../../-webkit-overflow-scrolling) value `touch`.
- Element with a [`will-change`](../../will-change) value specifying any property that would create a stacking context on non-initial value (see [this post](https://dev.opera.com/articles/css-will-change-property/)).
- Element with a [`contain`](../../contain) value of `layout`, or `paint`, or a composite value that includes either of them (i.e. `contain: strict`, `contain: content`).

Within a stacking context, child elements are stacked according to the same rules previously explained. Importantly, the `z-index` values of its child stacking contexts only have meaning in this parent. Stacking contexts are treated atomically as a single unit in the parent stacking context.

In summary:

- Stacking contexts can be contained in other stacking contexts, and together create a hierarchy of stacking contexts.
- Each stacking context is completely independent of its siblings: only descendant elements are considered when stacking is processed.
- Each stacking context is self-contained: after the element's contents are stacked, the whole element is considered in the stacking order of the parent stacking context.

**Note:** The hierarchy of stacking contexts is a subset of the hierarchy of HTML elements because only certain elements create stacking contexts. We can say that elements that do not create their own stacking contexts are _assimilated_ by the parent stacking context.

## The example

<img src="data:image/png;base64,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" alt="Example of stacking rules modified using z-index" width="465" height="396" />

In this example, every positioned element creates its own stacking context, because of their positioning and `z-index` values. The hierarchy of stacking contexts is organized as follows:

- Root
  - DIV \#1
  - DIV \#2
  - DIV \#3
    - DIV \#4
    - DIV \#5
    - DIV \#6

It is important to note that DIV \#4, DIV \#5 and DIV \#6 are children of DIV \#3, so stacking of those elements is completely resolved within DIV\#3. Once stacking and rendering within DIV \#3 is completed, the whole DIV \#3 element is passed for stacking in the root element with respect to its sibling's DIV.

**Notes:**

- DIV \#4 is rendered under DIV \#1 because DIV \#1's z-index (5) is valid within the stacking context of the root element, while DIV \#4's z-index (6) is valid within the stacking context of DIV \#3. So, DIV \#4 is under DIV \#1, because DIV \#4 belongs to DIV \#3, which has a lower z-index value.
- For the same reason DIV \#2 (z-index 2) is rendered under DIV\#5 (z-index 1) because DIV \#5 belongs to DIV \#3, which has an higher z-index value.
- DIV \#3's z-index is 4, but this value is independent from z-index of DIV \#4, DIV \#5 and DIV \#6, because it belongs to a different stacking context.
- An easy way to figure out the _rendering order_ of stacked elements along the Z axis is to think of it as a "version number" of sorts, where child elements are minor version numbers underneath their parent's major version numbers. This way we can easily see how an element with a z-index of 1 (DIV \#5) is stacked above an element with a z-index of 2 (DIV \#2), and how an element with a z-index of 6 (DIV \#4) is stacked below an element with a z-index of 5 (DIV \#1). In our example (sorted according to the final rendering order):
  - Root
    - DIV \#2 - z-index is 2
    - DIV \#3 - z-index is 4
      - DIV \#5 - z-index is 1, stacked under an element with a z-index of 4, which results in a rendering order of 4.1
      - DIV \#6 - z-index is 3, stacked under an element with a z-index of 4, which results in a rendering order of 4.3
      - DIV \#4 - z-index is 6, stacked under an element with a z-index of 4, which results in a rendering order of 4.6
    - DIV \#1 - z-index is 5

## Example

### HTML

    <div id="div1">
      <h1>Division Element #1</h1>
      <code>position: relative;<br/>
      z-index: 5;</code>
    </div>

    <div id="div2">
      <h1>Division Element #2</h1>
      <code>position: relative;<br/>
      z-index: 2;</code>
    </div>

    <div id="div3">
      <div id="div4">
        <h1>Division Element #4</h1>
        <code>position: relative;<br/>
        z-index: 6;</code>
      </div>

      <h1>Division Element #3</h1>
      <code>position: absolute;<br/>
      z-index: 4;</code>

      <div id="div5">
        <h1>Division Element #5</h1>
        <code>position: relative;<br/>
        z-index: 1;</code>
      </div>

      <div id="div6">
        <h1>Division Element #6</h1>
        <code>position: absolute;<br/>
        z-index: 3;</code>
      </div>
    </div>

### CSS

    * {
      margin: 0;
    }
    html {
      padding: 20px;
      font: 12px/20px Arial, sans-serif;
    }
    div {
      opacity: 0.7;
      position: relative;
    }
    h1 {
      font: inherit;
      font-weight: bold;
    }
    #div1,
    #div2 {
      border: 1px dashed #696;
      padding: 10px;
      background-color: #cfc;
    }
    #div1 {
      z-index: 5;
      margin-bottom: 190px;
    }
    #div2 {
      z-index: 2;
    }
    #div3 {
      z-index: 4;
      opacity: 1;
      position: absolute;
      top: 40px;
      left: 180px;
      width: 330px;
      border: 1px dashed #900;
      background-color: #fdd;
      padding: 40px 20px 20px;
    }
    #div4,
    #div5 {
      border: 1px dashed #996;
      background-color: #ffc;
    }
    #div4 {
      z-index: 6;
      margin-bottom: 15px;
      padding: 25px 10px 5px;
    }
    #div5 {
      z-index: 1;
      margin-top: 15px;
      padding: 5px 10px;
    }
    #div6 {
      z-index: 3;
      position: absolute;
      top: 20px;
      left: 180px;
      width: 150px;
      height: 125px;
      border: 1px dashed #009;
      padding-top: 125px;
      background-color: #ddf;
      text-align: center;
    }

### Result

## See also

- [Stacking without the z-index property](stacking_without_z-index): The stacking rules that apply when `z-index` is not used.
- [Stacking with floated blocks](stacking_and_float): How floating elements are handled with stacking.
- [Using z-index](adding_z-index): How to use `z-index` to change default stacking.
- [Stacking context example 1](stacking_context_example_1): 2-level HTML hierarchy, `z-index` on the last level
- [Stacking context example 2](stacking_context_example_2): 2-level HTML hierarchy, `z-index` on all levels
- [Stacking context example 3](stacking_context_example_3): 3-level HTML hierarchy, `z-index` on the second level

## Original Document Information

- Author(s): Paolo Lombardi
- This article is the English translation of an article I wrote in Italian for [YappY](http://www.yappy.it). I grant the right to share all the content under the [Creative Commons: Attribution-Sharealike license](https://creativecommons.org/licenses/by-sa/2.0/).
- Last Updated Date: July 9, 2005

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context</a>
