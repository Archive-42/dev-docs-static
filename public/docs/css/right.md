# right

The `right` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property participates in specifying the horizontal position of a [positioned element](position). It has no effect on non-positioned elements.

## Syntax

    /* <length> values */
    right: 3px;
    right: 2.4em;

    /* <percentage>s of the width of the containing block */
    right: 10%;

    /* Keyword value */
    right: auto;

    /* Global values */
    right: inherit;
    right: initial;
    right: unset;

### Values

[`<length>`](length)  
A negative, null, or positive [`<length>`](length) that represents:

- for _absolutely positioned elements_, the distance to the right edge of the containing block.
- for _relatively positioned elements_, the distance that the element is moved to the left of its normal position.

[`<percentage>`](percentage)  
A [`<percentage>`](percentage) of the containing block's width.

`auto`  
Specifies that:

- for _absolutely positioned elements_, the position of the element is based on the [`left`](left) property, while `width: auto` is treated as a width based on the content; or if `left` is also `auto`, the element is positioned where it should horizontally be positioned if it were a static element.
- for _relatively positioned elements_, the distance of the element from its normal position is based on the [`left`](left) property; or if `left` is also `auto`, the element is not moved horizontally at all.

`inherit`  
Specifies that the value is the same as the computed value from its parent element (which might not be its containing block). This computed value is then handled as if it were a [`<length>`](length), [`<percentage>`](percentage), or the `auto` keyword.

## Description

The effect of `right` depends on how the element is positioned (i.e., the value of the [`position`](position) property):

- When `position` is set to `absolute` or `fixed`, the `right` property specifies the distance between the element's right edge and the right edge of its containing block.
- When `position` is set to `relative`, the `right` property specifies the distance the element's right edge is moved to the left from its normal position.
- When `position` is set to `sticky`, the `right` property is used to compute the sticky-constraint rectangle.
- When `position` is set to `static`, the `right` property has _no effect_.

When both [`left`](left) and `right` are defined, if not prevented from doing so by other properties, the element will stretch to satisfy both. If the element cannot stretch to satisfy both -- for example, if a `width` is declared -- the position of the element is _over-constrained_. When this is the case, the `left` value has precedence when the container is left-to-right; the `right` value has precedence when the container is right-to-left.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>positioned elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>if specified as a length, the corresponding absolute length; if specified as a percentage, the specified value; otherwise, <code>auto</code></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <length> | <percentage> | auto

## Examples

### Absolute and relative positioning using right

#### HTML

    <div id="relative">Relatively positioned</div>
    <div id="absolute">Absolutely positioned</div>

#### CSS

    #relative {
      width: 100px;
      height: 100px;
      background-color: #FFC7E4;
      position: relative;
      top: 20px;
      left: 20px;
    }

    #absolute {
      width: 100px;
      height: 100px;
      background-color: #FFD7C2;
      position: absolute;
      bottom: 10px;
      right: 20px;
    }

#### Result

### Declaring both left and right

When both `left` and `right` are declared, the element will stretch to meet both, unless other constraints prevent it from doing so. If the element will not stretch or shrink to meet both. When the position of the element is _overspecified_, the precedence is based on the container's direction: The `left` will take precedence if the container's direction is left-to-right. The `right` will take precedence if the container's direction is right-to-left.

#### HTML

    <div id="parent">Parent
        <div id="noWidth">No width</div>
        <div id="width">width: 100px</div>
    </div>

#### CSS

    div {
      outline: 1px solid #CCCCCC;
    }
    #parent {
      width: 200px;
      height: 200px;
      background-color: #FFC7E4;
      position: relative;
    }
    /* declare both a left and a right */
    #width,
    #noWidth {
      background-color: #C2FFD7;
      position: absolute;
      left: 0;
      right: 0;
    }
    /* declare a width */
    #width {
      width: 100px;
      top: 60px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-position-3/#propdef-right">CSS Positioned Layout Module Level 3<br />
<span class="small">The definition of 'right' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds behavior for sticky positioning.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/visuren.html#propdef-right">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'right' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`right`

1

12

1

5.5

5

1

1

18

4

14

1

1.0

## See also

- [`inset`](inset), the shorthand for all related properties: [`top`](top), [`bottom`](bottom), [`left`](left), and [`right`](right)
- The mapped logical properties: [`inset-block-start`](inset-block-start), [`inset-block-end`](inset-block-end), [`inset-inline-start`](inset-inline-start), and [`inset-inline-end`](inset-inline-end) and the shorthands [`inset-block`](inset-block) and [`inset-inline`](inset-inline)
- [`position`](position)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/right" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/right</a>
