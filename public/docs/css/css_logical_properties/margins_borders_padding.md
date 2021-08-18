# Logical properties for margins, borders and padding

The [Logical Properties and Values specification](https://drafts.csswg.org/css-logical/) defines flow-relative mappings for the various margin, border, and padding properties and their shorthands. In this guide we take a look at these.

If you have looked at the main page for [CSS Logical Properties and Values](../css_logical_properties) you will see there are a huge number of properties listed. This is mostly due to the fact that there are four longhand values each for margin, border, and padding side, plus all the shorthand values.

## Mappings for margins, borders, and padding

The specification details mappings for each logical value to a physical counterpart. In the table below I have given these mapped values assuming that the [`writing-mode`](../writing-mode) in use is `horizontal-tb` — with a left to right direction. The inline direction therefore runs horizontally — left to right — and [`margin-inline-start`](../margin-inline-start) would be equivalent to [`margin-left`](../margin-left).

If you were using a `horizontal-tb` writing mode with a right-to-left text direction then [`margin-inline-start`](../margin-inline-start) would be the same as [`margin-right`](../margin-right), and in a vertical writing mode it would be the same as using [`margin-top`](../margin-top).

<table><thead><tr class="header"><th>Logical property</th><th>Physical Property</th></tr></thead><tbody><tr class="odd"><td><a href="../border-block-end"><code>border-block-end</code></a></td><td><a href="../border-bottom"><code>border-bottom</code></a></td></tr><tr class="even"><td><a href="../border-block-end-color"><code>border-block-end-color</code></a></td><td><a href="../border-bottom-color"><code>border-bottom-color</code></a></td></tr><tr class="odd"><td><a href="../border-block-end-style"><code>border-block-end-style</code></a></td><td><a href="../border-bottom-style"><code>border-bottom-style</code></a></td></tr><tr class="even"><td><a href="../border-block-end-width"><code>border-block-end-width</code></a></td><td><a href="../border-bottom-width"><code>border-bottom-width</code></a></td></tr><tr class="odd"><td><a href="../border-block-start"><code>border-block-start</code></a></td><td><a href="../border-top"><code>border-top</code></a></td></tr><tr class="even"><td><a href="../border-block-start-color"><code>border-block-start-color</code></a></td><td><a href="../border-top-color"><code>border-top-color</code></a></td></tr><tr class="odd"><td><a href="../border-block-start-style"><code>border-block-start-style</code></a></td><td><a href="../border-top-style"><code>border-top-style</code></a></td></tr><tr class="even"><td><a href="../border-block-start-width"><code>border-block-start-width</code></a></td><td><a href="../border-top-width"><code>border-top-width</code></a></td></tr><tr class="odd"><td><a href="../border-inline-end"><code>border-inline-end</code></a></td><td><a href="../border-right"><code>border-right</code></a></td></tr><tr class="even"><td><a href="../border-inline-end-color"><code>border-inline-end-color</code></a></td><td><a href="../border-right-color"><code>border-right-color</code></a></td></tr><tr class="odd"><td><a href="../border-inline-end-style"><code>border-inline-end-style</code></a></td><td><a href="../border-right-style"><code>border-right-style</code></a></td></tr><tr class="even"><td><a href="../border-inline-end-width"><code>border-inline-end-width</code></a></td><td><a href="../border-right-width"><code>border-right-width</code></a></td></tr><tr class="odd"><td><a href="../border-inline-start"><code>border-inline-start</code></a></td><td><a href="../border-left"><code>border-left</code></a></td></tr><tr class="even"><td><a href="../border-inline-start-color"><code>border-inline-start-color</code></a></td><td><a href="../border-left-color"><code>border-left-color</code></a></td></tr><tr class="odd"><td><a href="../border-inline-start-style"><code>border-inline-start-style</code></a></td><td><a href="../border-left-style"><code>border-left-style</code></a></td></tr><tr class="even"><td><a href="../border-inline-start-width"><code>border-inline-start-width</code></a></td><td><a href="../border-left-width"><code>border-left-width</code></a></td></tr><tr class="odd"><td><a href="../border-start-start-radius"><code>border-start-start-radius</code></a></td><td><a href="../border-top-left-radius"><code>border-top-left-radius</code></a></td></tr><tr class="even"><td><a href="../border-start-end-radius"><code>border-start-end-radius</code></a></td><td><a href="../border-bottom-left-radius"><code>border-bottom-left-radius</code></a></td></tr><tr class="odd"><td><a href="../border-end-start-radius"><code>border-end-start-radius</code></a></td><td><a href="../border-top-right-radius"><code>border-top-right-radius</code></a></td></tr><tr class="even"><td><a href="../border-end-end-radius"><code>border-end-end-radius</code></a></td><td><a href="../border-bottom-right-radius"><code>border-bottom-right-radius</code></a></td></tr><tr class="odd"><td><a href="../margin-block-end"><code>margin-block-end</code></a></td><td><a href="../margin-bottom"><code>margin-bottom</code></a></td></tr><tr class="even"><td><a href="../margin-block-start"><code>margin-block-start</code></a></td><td><a href="../margin-top"><code>margin-top</code></a></td></tr><tr class="odd"><td><a href="../margin-inline-end"><code>margin-inline-end</code></a></td><td><a href="../margin-right"><code>margin-right</code></a></td></tr><tr class="even"><td><a href="../margin-inline-start"><code>margin-inline-start</code></a></td><td><a href="../margin-left"><code>margin-left</code></a></td></tr><tr class="odd"><td><a href="../padding-block-end"><code>padding-block-end</code></a></td><td><a href="../padding-bottom"><code>padding-bottom</code></a></td></tr><tr class="even"><td><a href="../padding-block-start"><code>padding-block-start</code></a></td><td><a href="../padding-top"><code>padding-top</code></a></td></tr><tr class="odd"><td><a href="../padding-inline-end"><code>padding-inline-end</code></a></td><td><a href="../padding-right"><code>padding-right</code></a></td></tr><tr class="even"><td><a href="../padding-inline-start"><code>padding-inline-start</code></a></td><td><a href="../padding-left"><code>padding-left</code></a></td></tr></tbody></table>

There are also some additional shorthands, made possible because we have the ability to target both block or both inline edges of the box simultaneously. These shorthands have no physical equivalent.

<table><thead><tr class="header"><th>Property</th><th>Purpose</th></tr></thead><tbody><tr class="odd"><td><a href="../border-block"><code>border-block</code></a></td><td>Sets <a href="../border-color"><code>border-color</code></a>, <a href="../border-style"><code>border-style</code></a>, and <a href="../border-width"><code>border-width</code></a> for both block borders.</td></tr><tr class="even"><td><a href="../border-block-color"><code>border-block-color</code></a></td><td>Sets <code>border-color</code> for both block borders.</td></tr><tr class="odd"><td><a href="../border-block-style"><code>border-block-style</code></a></td><td>Sets <code>border-style</code> for both block borders.</td></tr><tr class="even"><td><a href="../border-block-width"><code>border-block-width</code></a></td><td>Sets <code>border-width</code> for both block borders.</td></tr><tr class="odd"><td><a href="../border-inline"><code>border-inline</code></a></td><td>Sets <code>border-color</code>, <code>-style</code>, and <code>-width</code> for both inline borders.</td></tr><tr class="even"><td><a href="../border-inline-color"><code>border-inline-color</code></a></td><td>Sets <code>border-color</code> for both inline borders.</td></tr><tr class="odd"><td><a href="../border-inline-style"><code>border-inline-style</code></a></td><td>Sets <code>border-style</code> for both inline borders.</td></tr><tr class="even"><td><a href="../border-inline-width"><code>border-inline-width</code></a></td><td>Sets <code>border-width</code> for both inline borders.</td></tr><tr class="odd"><td><a href="../margin-block"><code>margin-block</code></a></td><td>Sets all the block <a href="../margin"><code>margin</code></a>s.</td></tr><tr class="even"><td><a href="../margin-inline"><code>margin-inline</code></a></td><td>Sets all the inline <code>margin</code>s.</td></tr><tr class="odd"><td><a href="../padding-block"><code>padding-block</code></a></td><td>Sets the block <a href="../padding"><code>padding</code></a>.</td></tr><tr class="even"><td><a href="../padding-inline"><code>padding-inline</code></a></td><td>Sets the inline <code>padding</code>.</td></tr></tbody></table>

## Margin examples

The mapped margin properties of [`margin-inline-start`](../margin-inline-start), [`margin-inline-end`](../margin-inline-end), [`margin-block-start`](../margin-block-start), and [`margin-inline-end`](../margin-inline-end) can be used instead of their physical counterparts.

In the example below I have created two boxes and added different sized margins to each edge. I have added an extra container with a border in order to make the margin more obvious to see.

One box uses physical properties and the other logical properties. Try changing the [`direction`](../direction) property to `rtl` to cause the boxes to display in a right-to-left direction, the margins on the first box will stay in the same place, while the margins on the inline dimension of the second box will switch.

You can also try changing the `writing-mode` from `horizontal-tb` to `vertical-rl`. Again, notice how the margins stay in the same place for the first box, but switch around to follow the text direction in the second.

### Margin shorthands

As we can now target both sides of a box — either both inline sides or both block sides — there are new shorthands available, [`margin-inline`](../margin-inline) and [`margin-block`](../margin-block), which accept two values. The first value will apply to the start of that dimension, the second to the end. If you only use one value it is applied to both.

In a horizontal writing mode this CSS would apply a 5px margin to the top of the box and a 10px margin to the bottom.

    .box {
      margin-block: 5px 10px;
    }

**Note**: The shorthand properties `margin-inline` and `margin-block` shipped in Firefox 66. As these are new properties check browser support before using.

## Padding examples

The mapped padding properties of [`padding-inline-start`](../padding-inline-start), [`padding-inline-end`](../padding-inline-end), [`padding-block-start`](../padding-block-start), and [`padding-inline-end`](../padding-inline-end) can be used instead of their physical counterparts.

In the example below I have two boxes, one of which is using physical padding properties and the other logical padding properties. With a `writing-mode` of `horizontal-tb`, both boxes should appear the same.

Try changing the `direction` property to `rtl` to cause the boxes to display in a right-to-left direction. The padding on the first box will stay in the same place, whereas the padding on the inline dimension of the second box will switch.

You can also try changing the `writing-mode` from `horizontal-tb` to `vertical-rl`. Again, notice how the padding stays in the same place for the first box, but switches around to follow the text direction in the second.

### Padding shorthands

As with margin, there are two-value shorthands for padding — [`padding-inline`](../padding-inline) and [`padding-block`](../padding-block) — which allow you to set the padding of the two inline, and two block dimensions, respectively.

In a horizontal `writing-mode` this CSS would apply `5px` of padding to the top of the box and 10px of padding to the bottom:

    .box {
      padding-block: 5px 10px;
    }

**Note**: The shorthand properties `padding-inline` and `padding-block` shipped in Firefox 66. As these are new properties check browser support before using.

## Border examples

The border properties are the main reason that Logical Properties and Values seems to have so many properties, as we have the longhands for the color, width, and style of the border on each side of a box, along with the shorthand to set all three at once for each side. As with margin and padding we have a mapped version of each physical property.

The demo below uses some longhands and three shorthand values. As with the other demos try changing the `direction` property to `rtl` to cause the boxes to display in a right-to-left direction, or changing the `writing-mode` from `horizontal-tb` to `vertical-rl`.

### New border shorthands

There are two-value shorthands to set the width, style and, color of the block or inline dimension, and two-value shorthands to set all three values in the block or inline dimension. The below code, in a horizontal writing mode, would give you a 2px green solid border on the top and bottom of the box, and a 4px dotted purple border on the left and right.

    .box {
      border-block: 2px solid green;
      border-inline-width: 4px;
      border-inline-style: dotted;
      border-inline-color: rebeccapurple;
    }

**Note**: these two value shorthands shipped in Firefox 66, check browser support before using as other browsers may not have implemented them yet.

### Flow relative border-radius properties

The specification has fairly recently added flow-relative values for the [`border-radius`](../border-radius) longhands. These have not yet been implemented by any browser. The below example, in a horizontal `writing-mode`, would set the top-right border radius to 1em, the bottom-right to 0, the bottom-left to 20px and the top-left to 40px.

    .box {
      border-end-start-radius: 1em;
      border-end-end-radius: 0;
      border-start-end-radius: 20px;
      border-start-start-radius: 40px;
    }

## Indicating logical values for the 4-value shorthand syntax

The specification makes a suggestion for the four-value shorthands such as the `margin` property, however the final decision on how this should be indicated is as yet unresolved, and is discussed in [this issue](https://github.com/w3c/csswg-drafts/issues/1282).

Using any four-value shorthand such as margin, padding, or border will currently use the physical versions, so if following the flow of the document is important, use the longhand properties for the time being.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Logical_Properties/Margins_borders_padding" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Logical_Properties/Margins_borders_padding</a>
