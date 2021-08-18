# Stacking context example 2

« [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) « [Understanding CSS z-index](../understanding_z_index)

## Stacking context example 2

This is a very simple example, but it is the key for understanding the concept of _stacking context_. There are the same four DIVs of the previous example, but now z-index properties are assigned on both levels of the hierarchy.

You can see that DIV \#2 (z-index: 2) is above DIV \#3 (z-index: 1), because they both belong to the same stacking context (the root one), so z-index values rule how elements are stacked.

What can be considered strange is that DIV \#2 (z-index: 2) is above DIV \#4 (z-index: 10), despite their z-index values. The reason is that they do not belong to the same stacking context. DIV \#4 belongs to the stacking context created by DIV \#3, and as explained previously DIV \#3 (and all its content) is under DIV \#2.

To better understand the situation, this is the stacking context hierarchy:

- root stacking context
  - DIV \#2 (z-index 2)
  - DIV \#3 (z-index 1)
    - DIV \#4 (z-index 10)

**Note:** It is worth remembering that in general the HTML hierarchy is different from the stacking context hierarchy. In the stacking context hierarchy, elements that do not create a stacking context are collapsed on their parent.

## Example source code

    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
    <html>
    <head><style type="text/css">

    div { font: 12px Arial; }

    span.bold { font-weight: bold; }

    #div2 { z-index: 2; }
    #div3 { z-index: 1; }
    #div4 { z-index: 10; }

    #div1,#div3 {
       height: 80px;
       position: relative;
       border: 1px dashed #669966;
       background-color: #ccffcc;
       padding-left: 5px;
    }

    #div2 {
       opacity: 0.8;
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

    </style></head>

    <body>

        <br />

        <div id="div1"><br />
            <span class="bold">DIV #1</span><br />
            position: relative;
            <div id="div2"><br />
                <span class="bold">DIV #2</span><br />
                position: absolute;<br />
                z-index: 2;
            </div>
        </div>

        <br />

        <div id="div3"><br />
            <span class="bold">DIV #3</span><br />
            position: relative;<br />
            z-index: 1;
            <div id="div4"><br />
                <span class="bold">DIV #4</span><br />
                position: absolute;<br />
                z-index: 10;
            </div>
        </div>

    </body>
    </html>

## See also

- [Stacking without the z-index property](stacking_without_z-index): The stacking rules that apply when `z-index` is not used.
- [Stacking with floated blocks](stacking_and_float): How floating elements are handled with stacking.
- [Using z-index](adding_z-index): How to use `z-index` to change default stacking.
- [The stacking context](the_stacking_context): Notes on the stacking context.
- [Stacking context example 1](stacking_context_example_1): 2-level HTML hierarchy, `z-index` on the last level
- [Stacking context example 3](stacking_context_example_3): 3-level HTML hierarchy, `z-index` on the second level

## Original Document Information

- Author(s): Paolo Lombardi
- This article is the English translation of an article I wrote in Italian for [YappY](http://www.yappy.it). I grant the right to share all the content under the [Creative Commons: Attribution-Sharealike license](https://creativecommons.org/licenses/by-sa/2.0/).
- Last Updated Date: July 9, 2005

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/Stacking_context_example_2" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/Stacking_context_example_2</a>
