# CSS Overflow

The **CSS Overflow** module contains the features of CSS relating to scrollable overflow handling in visual media. In CSS overflow happens when the content of a box extends past one or more of the box's edges.

## Ink overflow and scrollable overflow

There are two types of overflow that you might encounter in CSS. The first is described as **ink overflow**. This is the overflow of painting effects which do not affect layout or otherwise extend the scrollable overflow region, such as box shadows, border images, text decoration, overhanging glyphs, outlines, etc.

The overflow that we sometimes need to manage in CSS is described as **scrollable overflow**. This is the content appearing outside of the box for which scrolling mechanisms need to be provided. The overflow properties are how we can control what happens when content overflows a box.

## Basic example

The following interactive example shows how changing the value of the `overflow` property, changes how the overflow of a fixed height box is dealt with.

## Reference

### CSS properties

- [`overflow`](overflow)
- [`overflow-block`](overflow-block)
- [`overflow-inline`](overflow-inline)
- [`overflow-x`](overflow-x)
- [`overflow-y`](overflow-y)
- [`text-overflow`](text-overflow)
- <span class="page-not-created">`block-overflow`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- <span class="page-not-created">`line-clamp`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- <span class="page-not-created">`max-lines`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- <span class="page-not-created">`continue`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

### Non-standard properties

- [`-webkit-line-clamp`](-webkit-line-clamp) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>

## Specifications

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-overflow-3/#propdef-overflow">CSS Overflow Module Level 3<br />
<span class="small">The definition of 'overflow' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td><p>Changed syntax to allow one or two keywords instead of only one</p></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/visufx.html#overflow">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'overflow' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## See also

- Properties for controlling the look of scrollbars [`scrollbar-width`](scrollbar-width) and [`scrollbar-color`](scrollbar-color)
- How to [Debug scrollable overflow](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Debug_Scrollable_Overflow).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Overflow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Overflow</a>
