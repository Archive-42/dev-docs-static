# Logical properties for sizing

In this guide we will explain the flow-relative mappings between physical dimension properties and logical properties used for sizing elements on our pages.

When specifying the size of an item, the [Logical Properties and Values](https://drafts.csswg.org/css-logical/) specification gives you the ability to indicate sizing as it relates to the flow of text (inline and block) rather than physical sizing which relates to the physical dimensions of horizontal and vertical (e.g. left and right). While these flow relative mappings may well become the default for many of us, in a design you may well use both physical and logical sizing. You might want some features to always relate to the physical dimensions whatever the writing mode.

## Mappings for dimensions

The table below provides mappings between logical and physical properties. These mappings assume that you are in a `horizontal-tb` writing mode, such as English or Arabic, in which case [`width`](../width) would be mapped to [`inline-size`](../inline-size).

If you were in a vertical writing mode then [`inline-size`](../inline-size) would be mapped to [`height`](../height).

<table><thead><tr class="header"><th>Logical Property</th><th>Physical Property</th></tr></thead><tbody><tr class="odd"><td><a href="../inline-size"><code>inline-size</code></a></td><td><a href="../width"><code>width</code></a></td></tr><tr class="even"><td><a href="../block-size"><code>block-size</code></a></td><td><a href="../height"><code>height</code></a></td></tr><tr class="odd"><td><a href="../min-inline-size"><code>min-inline-size</code></a></td><td><a href="../min-width"><code>min-width</code></a></td></tr><tr class="even"><td><a href="../min-block-size"><code>min-block-size</code></a></td><td><a href="../min-height"><code>min-height</code></a></td></tr><tr class="odd"><td><a href="../max-inline-size"><code>max-inline-size</code></a></td><td><a href="../max-width"><code>max-width</code></a></td></tr><tr class="even"><td><a href="../max-block-size"><code>max-block-size</code></a></td><td><a href="../max-height"><code>max-height</code></a></td></tr></tbody></table>

## Width and height example

The logical mappings for [`width`](../width) and [`height`](../height) are [`inline-size`](../inline-size), which sets the length in the inline dimension and [`block-size`](../block-size), which sets the length in the block dimension. When working in English, replacing `width` with `inline-size` and `height` with `block-size` will give the same layout.

In the live example below I have set the Writing Mode to `horizontal-tb`. Change it to `vertical-rl` and you will see that the first example — which uses `width` and `height` — remains the same size in each dimension, despite the text becoming vertical. The second example — which uses `inline-size` and `block-size` — will follow the text direction as if the entire block has rotated.

## Min-width and min-height example

There are also mappings for [`min-width`](../min-width) and [`min-height`](../min-height) — these are [`min-inline-size`](../min-inline-size) and [`min-block-size`](../min-block-size). These work in the same way as the `inline-size` and `block-size` properties, but setting a minimum rather than a fixed size.

Try changing the example below to `vertical-rl`, as with the first example, to see the effect it has. I am using `min-height` in the first example and `min-block-size` in the second.

## Max-width and max-height example

Finally you can use [`max-inline-size`](../max-inline-size) and [`max-block-size`](../max-block-size) as logical replacements for [`max-width`](../max-width) and [`max-height`](../max-height). Try playing with the below example in the same way as before.

## Logical keywords for resize

The [`resize`](../resize) property sets whether or not an item can be resized and has physical values of `horizontal` and `vertical`. The `resize` property also has logical keyword values. Using `resize: inline` allows resizing in the inline dimension and `resize: block` allow resizing in the block dimension.

The keyword value of `both` for the resize property works whether you are thinking physically or logically. It sets both dimensions at once. Try playing with the below example.

Note that currently the logical values for resize are only supported by Firefox.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Logical_Properties/Sizing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Logical_Properties/Sizing</a>
