# left

The `left` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property participates in specifying the horizontal position of a [positioned element](position). It has no effect on non-positioned elements.

## Syntax

    /* <length> values */
    left: 3px;
    left: 2.4em;

    /* <percentage>s of the width of the containing block */
    left: 10%;

    /* Keyword value */
    left: auto;

    /* Global values */
    left: inherit;
    left: initial;
    left: unset;

### Values

[`<length>`](length)  
A negative, null, or positive [`<length>`](length) that represents:

- for _absolutely positioned elements_, the distance to the left edge of the containing block.
- for _relatively positioned elements_, the distance that the element is moved to the right of its normal position.

[`<percentage>`](percentage)  
A [`<percentage>`](percentage) of the containing block's width.

`auto`  
Specifies that:

- for _absolutely positioned elements_, the position of the element is based on the [`right`](right) property, while `width: auto` is treated as a width based on the content; or if `right` is also `auto`, the element is positioned where it should horizontally be positioned if it were a static element.
- for _relatively positioned elements_, the distance of the element from its normal position is based on the [`right`](right) property; or if `right` is also `auto`, the element is not moved horizontally at all.

`inherit`  
Specifies that the value is the same as the computed value from its parent element (which might not be its containing block). This computed value is then handled as if it were a [`<length>`](length), [`<percentage>`](percentage), or the `auto` keyword.

## Description

The effect of `left` depends on how the element is positioned (i.e., the value of the [`position`](position) property):

- When `position` is set to `absolute` or `fixed`, the `left` property specifies the distance between the element's left edge and the left edge of its containing block. (The containing block is the ancestor to which the element is relatively positioned.)
- When `position` is set to `relative`, the `left` property specifies the distance the element's left edge is moved to the right from its normal position.
- When `position` is set to `sticky`, the `left` property is used to compute the sticky-constraint rectangle.
- When `position` is set to `static`, the `left` property has _no effect_.

When both `left` and [`right`](right) are defined, and width constraints don't prevent it, the element will stretch to satisfy both. If the element cannot stretch to satisfy both, the position of the element is _overspecified_. When this is the case, the `left` value has precedence when the container is left-to-right; the `right` value has precedence when the container is right-to-left.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>positioned elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>if specified as a length, the corresponding absolute length; if specified as a percentage, the specified value; otherwise, <code>auto</code></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <length> | <percentage> | auto

## Examples

### Positioning elements

#### HTML

    <div id="wrap">
      <div id="example_1">
        <pre>
          position: absolute;
          left: 20px;
          top: 20px;
        </pre>
        <p>The only containing element for this div is the main window, so it positions itself in relation to it.</p>
      </div>

      <div id="example_2">
        <pre>
          position: relative;
          top: 0;
          right: 0;
        </pre>
        <p>Relative position in relation to its siblings.</p>
      </div>

      <div id="example_3">
        <pre>
          float: right;
          position: relative;
          top: 20px;
          left: 20px;
        </pre>
        <p>Relative to its sibling div above, but removed from flow of content.</p>

        <div id="example_4">
          <pre>
            position: absolute;
            bottom: 10px;
            right: 20px;
          </pre>
          <p>Absolute position inside of a parent with relative position</p>
        </div>

        <div id="example_5">
          <pre>
            position: absolute;
            right: 0;
            left: 0;
            top: 200px;
          </pre>
          <p>Absolute position with both left and right declared</p> </div>
      </div>
    </div>

#### CSS

    #wrap {
      width: 700px;
      margin: 0 auto;
      background: #5C5C5C;
    }

    pre {
      white-space: pre;
      white-space: pre-wrap;
      white-space: pre-line;
      word-wrap: break-word;
    }

    #example_1 {
      width: 200px;
      height: 200px;
      position: absolute;
      left: 20px;
      top: 20px;
      background-color: #D8F5FF;
    }

    #example_2 {
      width: 200px;
      height: 200px;
      position: relative;
      top: 0;
      right: 0;
      background-color: #C1FFDB;

    }
    #example_3 {
      width: 600px;
      height: 400px;
      position: relative;
      top: 20px;
      left: 20px;
      background-color: #FFD7C2;
    }

    #example_4 {
      width:200px;
      height:200px;
      position:absolute;
      bottom:10px;
      right:20px;
      background-color:#FFC7E4;
    }
    #example_5 {
      position: absolute;
      right: 0;
      left: 0;
      top: 100px;
      background-color: #D7FFC2;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-position-3/#propdef-left">CSS Positioned Layout Module Level 3<br />
<span class="small">The definition of 'left' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds behavior for sticky positioning.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/visuren.html#propdef-left">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'left' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`left`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/left" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/left</a>
