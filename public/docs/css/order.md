# order

The `order` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the order to lay out an item in a flex or grid container. Items in a container are sorted by ascending `order` value and then by their source code order.

## Syntax

    /* <integer> values */
    order: 5;
    order: -5;

    /* Global values */
    order: inherit;
    order: initial;
    order: unset;

Since `order` is only meant to affect the _visual order_ of elements and not their logical or tab order. `order` must not be used on non-visual media such as [speech](@media#speech).

### Values

[`<integer>`](integer)  
Represents the ordinal group to be used by the item.

## Accessibility concerns

Using the `order` property will create a disconnect between the visual presentation of content and DOM order. This will adversely affect users experiencing low vision navigating with the aid of assistive technology such as a screen reader. If the visual (css) order is important, then screen reader users will not have access to the correct reading order.

- [Flexbox & the keyboard navigation disconnect — Tink](https://tink.uk/flexbox-the-keyboard-navigation-disconnect/)
- [Source Order Matters | Adrian Roselli](https://adrianroselli.com/2015/09/source-order-matters.html)
- [MDN Understanding WCAG, Guideline 1.3 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.3_%e2%80%94_create_content_that_can_be_presented_in_different_ways)
- [Understanding Success Criterion 1.3.2 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-sequence.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>Flex items, grid items, and absolutely-positioned flex and grid container children</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>an <a href="integer#interpolation">integer</a></td></tr></tbody></table>

## Formal syntax

    <integer>

## Examples

### Ordering items in a flex container

This example uses CSS to create a classic two-sidebar layout surrounding a content block. The Flexible Box Layout Module automatically creates blocks of equal vertical size and uses as much horizontal space as available.

#### HTML

    <header>...</header>
    <main>
      <article>Article</article>
      <nav>Nav</nav>
      <aside>Aside</aside>
    </main>
    <footer>...</footer>

#### CSS

    main { display: flex;  text-align:center; }
    main > article { flex:1;        order: 2; }
    main > nav     { width: 200px;  order: 1; }
    main > aside   { width: 200px;  order: 3; }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-flexbox-1/#order-property">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'order' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>Flex items, grid items, and absolutely-positioned flex and grid container children</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>an <a href="integer#interpolation">integer</a></td></tr></tbody></table>

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

`order`

29

21

12

12

20

Since Firefox 28, multi-line flexbox is supported.

49

11

10

12.1

9

7

4.4

≤37

29

25

20

Since Firefox 28, multi-line flexbox is supported.

49

12.1

9

7

2.0

1.5

## See also

- CSS Flexbox Guide: _[Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)_
- CSS Flexbox Guide: _[Ordering flex items](css_flexible_box_layout/ordering_flex_items)_
- CSS Grid Guide: _[CSS Grid Layout and accessibility](css_grid_layout/css_grid_layout_and_accessibility)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/order" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/order</a>
