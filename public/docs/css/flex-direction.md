# flex-direction

The `flex-direction` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how flex items are placed in the flex container defining the main axis and the direction (normal or reversed).

Note that the values `row` and `row-reverse` are affected by the directionality of the flex container. If its [`dir`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-dir) attribute is `ltr`, `row` represents the horizontal axis oriented from the left to the right, and `row-reverse` from the right to the left; if the `dir` attribute is `rtl`, `row` represents the axis oriented from the right to the left, and `row-reverse` from the left to the right.

## Syntax

    /* The direction text is laid out in a line */
    flex-direction: row;

    /* Like <row>, but reversed */
    flex-direction: row-reverse;

    /* The direction in which lines of text are stacked */
    flex-direction: column;

    /* Like <column>, but reversed */
    flex-direction: column-reverse;

    /* Global values */
    flex-direction: inherit;
    flex-direction: initial;
    flex-direction: unset;

### Values

The following values are accepted:

`row`  
The flex container's main-axis is defined to be the same as the text direction. The **main-start** and **main-end** points are the same as the content direction.

`row-reverse`  
Behaves the same as `row` but the **main-start** and **main-end** points are permuted.

`column`  
The flex container's main-axis is the same as the block-axis. The **main-start** and **main-end** points are the same as the **before** and **after** points of the writing-mode.

`column-reverse`  
Behaves the same as `column` but the **main-start** and **main-end** are permuted.

## Accessibility concerns

Using the `flex-direction` property with values of `row-reverse` or `column-reverse` will create a disconnect between the visual presentation of content and DOM order. This will adversely affect users experiencing low vision navigating with the aid of assistive technology such as a screen reader. If the visual (CSS) order is important, then screen reader users will not have access to the correct reading order.

- [Flexbox & the keyboard navigation disconnect — Tink](https://tink.uk/flexbox-the-keyboard-navigation-disconnect/)
- [Source Order Matters | Adrian Roselli](https://adrianroselli.com/2015/09/source-order-matters.html)
- [MDN Understanding WCAG, Guideline 1.3 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.3_%e2%80%94_create_content_that_can_be_presented_in_different_ways)
- [Understanding Success Criterion 1.3.2 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-sequence.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>row</code></td></tr><tr class="even"><td>Applies to</td><td>flex containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    row | row-reverse | column | column-reverse

## Examples

### Reversing flex container columns and rows

#### HTML

    <h4>This is a Column-Reverse</h4>
    <div id="content">
      <div class="box" style="background-color:red;">A</div>
      <div class="box" style="background-color:lightblue;">B</div>
      <div class="box" style="background-color:yellow;">C</div>
    </div>
    <h4>This is a Row-Reverse</h4>
    <div id="content1">
      <div class="box1" style="background-color:red;">A</div>
      <div class="box1" style="background-color:lightblue;">B</div>
      <div class="box1" style="background-color:yellow;">C</div>
    </div>

#### CSS

    #content {
      width: 200px;
      height: 200px;
      border: 1px solid #c3c3c3;
      display: flex;
      flex-direction: column-reverse;
    }

    .box {
      width: 50px;
      height: 50px;
    }

    #content1 {
      width: 200px;
      height: 200px;
      border: 1px solid #c3c3c3;
      display: flex;
      flex-direction: row-reverse;
    }

    .box1 {
      width: 50px;
      height: 50px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-flexbox-1/#flex-direction-property">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'flex-direction' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`flex-direction`

29

21

12

12

20

\["Since Firefox 28, multi-line flexbox is supported.", "Before Firefox 81, overflow with `*-reverse` is unsupported. See [bug 1042151](https://bugzil.la/1042151)."\]

49

11

10

12.1

15

9

7

4.4

≤37

29

25

20

\["Since Firefox 28, multi-line flexbox is supported.", "Before Firefox 81, overflow with `*-reverse` is unsupported. See [bug 1042151](https://bugzil.la/1042151)."\]

49

12.1

14

9

7

2.0

1.5

## See also

- CSS Flexbox Guide: _[Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)_
- CSS Flexbox Guide: _[Ordering flex items](css_flexible_box_layout/ordering_flex_items)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction</a>
