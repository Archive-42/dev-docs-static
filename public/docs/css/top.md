# top

The `top` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property participates in specifying the vertical position of a [positioned element](position). It has no effect on non-positioned elements.

The effect of `top` depends on how the element is positioned (i.e., the value of the [`position`](position) property):

- When `position` is set to `absolute` or `fixed`, the `top` property specifies the distance between the element's outer margin of top edge and the inner border of the top edge of its containing block.
- When `position` is set to `relative`, the `top` property specifies the distance the element's top edge is moved below its normal position.
- When `position` is set to `sticky`, the `top` property is used to compute the sticky-constraint rectangle.
- When `position` is set to `static`, the `top` property has _no effect_.

When both `top` and [`bottom`](bottom) are specified, `position` is set to `absolute` or `fixed`, _and_ [`height`](height) is unspecified (either `auto` or `100%`) both the `top` and `bottom` distances are respected. In all other situations, if [`height`](height) is constrained in any way or `position` is set to `relative`, the `top` property takes precedence and the `bottom` property is ignored.

## Syntax

    /* <length> values */
    top: 3px;
    top: 2.4em;

    /* <percentage>s of the height of the containing block */
    top: 10%;

    /* Keyword value */
    top: auto;

    /* Global values */
    top: inherit;
    top: initial;
    top: unset;

### Values

[`<length>`](length)  
A negative, null, or positive [`<length>`](length) that represents:

- for _absolutely positioned elements_, the distance to the top edge of the containing block.
- for _relatively positioned elements_, the distance that the element is moved below its normal position.

[`<percentage>`](percentage)  
A [`<percentage>`](percentage) of the containing block's height.

`auto`  
Specifies that:

- for _absolutely positioned elements_, the position of the element is based on the [`bottom`](bottom) property, while `height: auto` is treated as a height based on the content; or if `bottom` is also `auto`, the element is positioned where it should vertically be positioned if it were a static element.
- for _relatively positioned elements_, the distance of the element from its normal position is based on the [`bottom`](bottom) property; or if `bottom` is also `auto`, the element is not moved vertically at all.

`inherit`  
Specifies that the value is the same as the computed value from its parent element (which might not be its containing block). This computed value is then handled as if it were a [`<length>`](length), [`<percentage>`](percentage), or the `auto` keyword.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>positioned elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the height of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>if specified as a length, the corresponding absolute length; if specified as a percentage, the specified value; otherwise, <code>auto</code></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <length> | <percentage> | auto

## Examples

### A positioned element set 10% from the top

    body {
      background: beige;
    }

    div {
      position: absolute;
      top: 10%;
      right: 40%;
      bottom: 20%;
      left: 15%;
      background: gold;
      border: 1px solid blue;
    }

    <div>The size of this content is determined by the position of its edges.</div>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-position-3/#propdef-top">CSS Positioned Layout Module Level 3<br />
<span class="small">The definition of 'top' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds behavior for sticky positioning.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/visuren.html#propdef-top">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'top' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`top`

1

12

1

5

In Internet Explorer versions before 7, when both `top` and `bottom` are specified, the element position is overconstrained and the `top` property has precedence; the computed value of `bottom` is set to `-top`, while its specified value is ignored.

6

1

≤37

18

4

14

1

1.0

## See also

- [`inset`](inset), the shorthand for all related properties: [`top`](top), [`bottom`](bottom), [`left`](left), and [`right`](right)
- The mapped logical properties: [`inset-block-start`](inset-block-start), [`inset-block-end`](inset-block-end), [`inset-inline-start`](inset-inline-start), and [`inset-inline-end`](inset-inline-end) and the shorthands [`inset-block`](inset-block) and [`inset-inline`](inset-inline)
- [`position`](position)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/top" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/top</a>
