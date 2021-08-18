# bottom

The `bottom` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property participates in setting the vertical position of a [positioned element](position). It has no effect on non-positioned elements.

The effect of `bottom` depends on how the element is positioned (i.e., the value of the [`position`](position) property):

- When `position` is set to `absolute` or `fixed`, the `bottom` property specifies the distance between the element's bottom edge and the bottom edge of its containing block.
- When `position` is set to `relative`, the `bottom` property specifies the distance the element's bottom edge is moved above its normal position.
- When `position` is set to `sticky`, the `bottom` property is used to compute the sticky-constraint rectangle.
- When `position` is set to `static`, the `bottom` property has _no effect_.

When both [`top`](top) and `bottom` are specified, `position` is set to `absolute` or `fixed`, _and_ [`height`](height) is unspecified (either `auto` or `100%`) both the `top` and `bottom` distances are respected. In all other situations, if [`height`](height) is constrained in any way or `position` is set to `relative`, the `top` property takes precedence and the `bottom` property is ignored.

## Syntax

    /* <length> values */
    bottom: 3px;
    bottom: 2.4em;

    /* <percentage>s of the height of the containing block */
    bottom: 10%;

    /* Keyword value */
    bottom: auto;

    /* Global values */
    bottom: inherit;
    bottom: initial;
    bottom: unset;

### Values

[`<length>`](length)  
A negative, null, or positive [`<length>`](length) that represents:

- for _absolutely positioned elements_, the distance to the bottom edge of the containing block.
- for _relatively positioned elements_, the distance that the element is moved above its normal position.

[`<percentage>`](percentage)  
A [`<percentage>`](percentage) of the containing block's height.

`auto`  
Specifies that:

- for _absolutely positioned elements_, the position of the element is based on the [`top`](top) property, while `height: auto` is treated as a height based on the content; or if `top` is also `auto`, the element is positioned where it should vertically be positioned if it were a static element.
- for _relatively positioned elements_, the distance of the element from its normal position is based on the [`top`](top) property; or if `top` is also `auto`, the element is not moved vertically at all.

`inherit`  
Specifies that the value is the same as the computed value from its parent element (which might not be its containing block). This computed value is then handled as if it were a [`<length>`](length), [`<percentage>`](percentage), or the `auto` keyword.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>positioned elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the height of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>if specified as a length, the corresponding absolute length; if specified as a percentage, the specified value; otherwise, <code>auto</code></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <length> | <percentage> | auto

## Examples

### Absolute and fixed positioning

This example demonstrates the difference in behavior of the `bottom` property, when [`position`](position) is `absolute` versus `fixed`.

#### HTML

    <p>This<br>is<br>some<br>tall,<br>tall,<br>tall,<br>tall,<br>tall<br>content.</p>
    <div class="fixed"><p>Fixed</p></div>
    <div class="absolute"><p>Absolute</p></div>

#### CSS

    p {
      font-size: 30px;
      line-height: 2em;
    }

    div {
      width: 48%;
      text-align: center;
      background: rgba(55,55,55,.2);
      border: 1px solid blue;
    }

    .absolute {
      position: absolute;
      bottom: 0;
      left: 0;
    }

    .fixed {
      position: fixed;
      bottom: 0;
      right: 0;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-position-3/#propdef-bottom">CSS Positioned Layout Module Level 3<br />
<span class="small">The definition of 'bottom' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds behavior for sticky positioning.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/visuren.html#choose-position">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'bottom' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`bottom`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/bottom" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/bottom</a>
