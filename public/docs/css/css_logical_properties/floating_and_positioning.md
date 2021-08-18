# Logical properties for floating and positioning

The [Logical Properties and Values specification](https://drafts.csswg.org/css-logical/) contains logical mappings for the physical values of [`float`](../float) and [`clear`](../clear), and also for the positioning properties used with [positioned layout](../css_positioning). This guide takes a look at how to use these.

## Mapped properties and values

The table below details the properties and values discussed in this guide along with their physical mappings. They assume a horizontal [`writing-mode`](../writing-mode), with a left-to-right direction.

<table><thead><tr class="header"><th>Logical property or value</th><th>Physical property or value</th></tr></thead><tbody><tr class="odd"><td><a href="../float"><code>float</code></a>: inline-start</td><td><a href="../float"><code>float</code></a>: left</td></tr><tr class="even"><td><a href="../float"><code>float</code></a>: inline-end</td><td><a href="../float"><code>float</code></a>: right</td></tr><tr class="odd"><td><a href="../clear"><code>clear</code></a>: inline-start</td><td><a href="../clear"><code>clear</code></a>: left</td></tr><tr class="even"><td><a href="../clear"><code>clear</code></a>: inline-end</td><td><a href="../clear"><code>clear</code></a>: right</td></tr><tr class="odd"><td><a href="../inset-inline-start"><code>inset-inline-start</code></a></td><td><a href="../left"><code>left</code></a></td></tr><tr class="even"><td><a href="../inset-inline-end"><code>inset-inline-end</code></a></td><td><a href="../right"><code>right</code></a></td></tr><tr class="odd"><td><a href="../inset-block-start"><code>inset-block-start</code></a></td><td><a href="../top"><code>top</code></a></td></tr><tr class="even"><td><a href="../inset-block-end"><code>inset-block-end</code></a></td><td><a href="../bottom"><code>bottom</code></a></td></tr><tr class="odd"><td><a href="../text-align"><code>text-align</code></a>: start</td><td><a href="../text-align"><code>text-align</code></a>: left</td></tr><tr class="even"><td><a href="../text-align"><code>text-align</code></a>: end</td><td><a href="../text-align"><code>text-align</code></a>: right</td></tr></tbody></table>

In addition to these mapped properties there are some additional shorthand properties made possible by being able to address block and inline dimensions. These have no mapping to physical properties, aside from the [`inset`](../inset) property.

<table><thead><tr class="header"><th>Logical property</th><th>Purpose</th></tr></thead><tbody><tr class="odd"><td><a href="../inset-inline"><code>inset-inline</code></a></td><td>Sets both of the above inset values for the inline dimension simultaneously.</td></tr><tr class="even"><td><a href="../inset-block"><code>inset-block</code></a></td><td>Sets both of the above inset values for the block dimension simultaneously.</td></tr><tr class="odd"><td><a href="../inset"><code>inset</code></a></td><td>Sets all four inset values simultaneously with physical mapping of multi-value.</td></tr></tbody></table>

## Float and clear example

The physical values used with the [`float`](../float) and [`clear`](../clear) properties are `left`, `right` and `both`. The Logical Properties specification defines the values `inline-start` and `inline-end` as mappings for `left` and `right`.

In the example below I have two boxes — the first has the box floated with `float: left`, the second with `float: inline-start`. If you change the `writing-mode` to `vertical-rl` or the `direction` to `rtl` you will see that the left-floated box always sticks to the left, whereas the `inline-start`-floated item follows the `direction` and `writing-mode`.

## Example: Inset properties for positioned layout

Positioning generally allows us to position an element in a manner relative to its containing block — we essentially inset the item relative to where it would fall based on normal flow. To do this we have historically used the physical properties [`top`](../top), [`right`](../right), [`bottom`](../bottom) and [`left`](../left).

These properties take a length or a percentage as a value, and relate to the user's screen dimensions.

New properties have been created in the Logical Properties specification for when you want the positioning to relate to the flow of text in your writing mode. These are as follows: [`inset-block-start`](../inset-block-start), [`inset-block-end`](../inset-block-end), [`inset-inline-start`](../inset-inline-start) and [`inset-inline-end`](../inset-inline-end).

In the below example I have used the `inset-block-start` and `inset-inline-end` properties to position the blue box using absolute positioning inside the area with the grey dotted border, which has `position: relative`. Change the `writing-mode` property to `vertical-rl`, or add `direction: rtl`, and see how the flow relative box stays with the text direction.

## New two- and four-value shorthands

As with other properties in the specification we have some new shorthand properties, which give the ability to set two or four values at once.

- [`inset`](../inset) — sets all four sides together with physical mapping.
- [`inset-inline`](../inset-inline) — sets both logical inline insets.
- [`inset-block`](../inset-block) — sets both logical block insets.

**Note**: The browsers that have implemented the Logical Properties specification have so far implemented the direct mappings and not the new shorthands. Look to the browser compatibility data section on each property page reference for more details.

## Example: Logical values for text-align

The [`text-align`](../text-align) property has logical values that relate to text direction — rather than using `left` and `right` we can use `start` and `end`. In the below example I have set `text-align: right` in the first block and `text-align: end` in the second.

If you change the value of `direction` to `rtl` you will see that the alignment stays to the right for the first block, but goes to the logical end on the left in the second.

This works in a more consistent way when using box alignment that uses start and end rather than physical directions for alignment.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Logical_Properties/Floating_and_positioning" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Logical_Properties/Floating_and_positioning</a>
