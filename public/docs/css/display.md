# display

The `display` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether an element is treated as a [block or inline element](css_flow_layout) and the layout used for its children, such as [flow layout](css_flow_layout), [grid](css_grid_layout) or [flex](css_flexible_box_layout).

Formally, the `display` property sets an element's inner and outer _display types_. The outer type sets an element's participation in [flow layout](css_flow_layout); the inner type sets the layout of children. Some values of `display` are fully defined in their own individual specifications; for example the detail of what happens when `display: flex` is declared is defined in the CSS Flexible Box Model specification. See [the table at the end of this document](#specifications) for all of the individual specifications.

## Syntax

The CSS `display` property is specified using keyword values.

    /* legacy values */
    display: block;
    display: inline;
    display: inline-block;
    display: flex;
    display: inline-flex;
    display: grid;
    display: inline-grid;
    display: flow-root;

    /* box generation */
    display: none;
    display: contents;

    /* two-value syntax */
    display: block flow;
    display: inline flow;
    display: inline flow-root;
    display: block flex;
    display: inline flex;
    display: block grid;
    display: inline grid;
    display: block flow-root;

    /* other values */
    display: table;
    display: table-row; /* all table elements have an equivalent CSS display value */
    display: list-item;

    /* Global values */
    display: inherit;
    display: initial;
    display: unset;

## Grouped values

The keyword values can be grouped into six value categories.

### Outside

[`<display-outside>`](display-outside)  
These keywords specify the element’s outer display type, which is essentially its role in flow layout.

Valid `<display-outside>` values:

`block`  
The element generates a block element box, generating line breaks both before and after the element when in the normal flow.

`inline`  
The element generates one or more inline element boxes that do not generate line breaks before or after themselves. In normal flow, the next element will be on the same line if there is space

**Note**: Browsers that support the two value syntax, on finding the outer value only, such as when `display: block` or `display: inline` is specified, will set the inner value to `flow`. This will result in expected behavior; for example if you specify an element to be block, you would expect that the children of that element would participate in block and inline normal flow layout.

### Inside

[`<display-inside>`](display-inside)  
These keywords specify the element’s inner display type, which defines the type of formatting context that its contents are laid out in (assuming it is a non-replaced element).

Valid `<display-inside>` values:

`flow` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The element lays out its contents using flow layout (block-and-inline layout).

If its outer display type is `inline` or `run-in`, and it is participating in a block or inline formatting context, then it generates an inline box. Otherwise it generates a block container box.

Depending on the value of other properties (such as [`position`](position), [`float`](float), or [`overflow`](overflow)) and whether it is itself participating in a block or inline formatting context, it either establishes a new [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context) (BFC) for its contents or integrates its contents into its parent formatting context.

`flow-root`  
The element generates a block element box that establishes a new [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context), defining where the formatting root lies.

`table`  
These elements behave like HTML [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) elements. It defines a block-level box.

`flex`  
The element behaves like a block element and lays out its content according to the [flexbox model](css_flexible_box_layout).

`grid`  
The element behaves like a block element and lays out its content according to the [grid model](css_grid_layout/basic_concepts_of_grid_layout).

`ruby` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The element behaves like an inline element and lays out its content according to the ruby formatting model. It behaves like the corresponding HTML [`<ruby>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ruby) elements.

**Note**: Browsers that support the two value syntax, on finding the inner value only, such as when `display: flex` or `display: grid` is specified, will set their outer value to `block`. This will result in expected behavior; for example if you specify an element to be `display: grid`, you would expect that the box created on the grid container would be a block level box.

### List Item

[`<display-listitem>`](display-listitem)  
The element generates a block box for the content and a separate list-item inline box.

A single value of `list-item` will cause the element to behave like a list item. This can be used together with [`list-style-type`](list-style-type) and [`list-style-position`](list-style-position).

`list-item` can also be combined with any [`<display-outside>`](display-outside) keyword and the `flow` or `flow-root` [`<display-inside>`](display-inside) keywords.

**Note**: In browsers that support the two-value syntax, if no inner value is specified it will default to `flow`. If no outer value is specified, the principal box will have an outer display type of `block`.

### Internal

[`<display-internal>`](display-internal)  
Some layout models such as `table` and `ruby` have a complex internal structure, with several different roles that their children and descendants can fill. This section defines those "internal" display values, which only have meaning within that particular layout mode.

Valid `<display-internal>` values:

`table-row-group`  
These elements behave like [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody) HTML elements.

`table-header-group`  
These elements behave like [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead) HTML elements.

`table-footer-group`  
These elements behave like [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot) HTML elements.

`table-row`  
These elements behave like [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr) HTML elements.

`table-cell`  
These elements behave like [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td) HTML elements.

`table-column-group`  
These elements behave like [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup) HTML elements.

`table-column`  
These elements behave like [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col) HTML elements.

`table-caption`  
These elements behave like [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption) HTML elements.

`ruby-base` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
These elements behave like [`<rb>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rb) HTML elements.

`ruby-text` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
These elements behave like [`<rt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rt) HTML elements.

`ruby-base-container` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
These elements behave like [`<rbc>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rbc) HTML elements generated as anonymous boxes.

`ruby-text-container` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
These elements behave like [`<rtc>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rtc) HTML elements.

### Box

[`<display-box>`](display-box)  
These values define whether an element generates display boxes at all.

Valid `<display-box>` values:

`contents`  
These elements don't produce a specific box by themselves. They are replaced by their pseudo-box and their child boxes. Please note that the CSS Display Level 3 spec defines how the `contents` value should affect "unusual elements" — elements that aren’t rendered purely by CSS box concepts such as replaced elements. See [Appendix B: Effects of display: contents on Unusual Elements](https://drafts.csswg.org/css-display/#unbox) for more details.

_Due to a bug in browsers this will currently remove the element from the accessibility tree — screen readers will not look at what's inside. See the [Accessibility concerns](#accessibility_concerns) section below for more details._

`none`  
Turns off the display of an element so that it has no effect on layout (the document is rendered as though the element did not exist). All descendant elements also have their display turned off.  
To have an element take up the space that it would normally take, but without actually rendering anything, use the [`visibility`](visibility) property instead.

### Legacy

[`<display-legacy>`](display-legacy)  
CSS 2 used a single-keyword syntax for the `display` property, requiring separate keywords for block-level and inline-level variants of the same layout mode.

Valid `<display-legacy>` values:

`inline-block`  
The element generates a block element box that will be flowed with surrounding content as if it were a single inline box (behaving much like a replaced element would).

It is equivalent to `inline flow-root`.

`inline-table`  
The `inline-table` value does not have a direct mapping in HTML. It behaves like an HTML [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) element, but as an inline box, rather than a block-level box. Inside the table box is a block-level context.

It is equivalent to `inline table`.

`inline-flex`  
The element behaves like an inline element and lays out its content according to the flexbox model.

It is equivalent to `inline flex`.

`inline-grid`  
The element behaves like an inline element and lays out its content according to the grid model.

It is equivalent to `inline grid`.

### Which syntax should you use now?

The Level 3 specification details two values for the `display` property — enabling the specification of the outer and inner display type explicitly — but this is not yet well-supported by browsers.

The `<display-legacy>` methods allow the same results with single keyword values, and should be favoured by developers until the two keyword values are better supported. For example, using two values you might specify an inline flex container as follows:

    .container {
      display: inline flex;
    }

This can currently be specified using a single value.

    .container {
      display: inline-flex;
    }

For more information on these changes to the specification, see the article [Adapting to the new two-value syntax of display](display/two-value_syntax_of_display).

### Global

    /* Global values */
    display: inherit;
    display: initial;
    display: unset;

## Description

The individual pages for the different types of value that `display` can have set on it feature multiple examples of those values in action — see the [Syntax](#syntax) section. In addition, see the following material, which covers the various values of display in depth.

- [Adapting to the new two-value syntax of display](display/two-value_syntax_of_display)

### CSS Flow Layout (display: block, display: inline)

- [Block and Inline Layout in Normal Flow](css_flow_layout/block_and_inline_layout_in_normal_flow)
- [Flow Layout and Overflow](css_flow_layout/flow_layout_and_overflow)
- [Flow Layout and Writing Modes](css_flow_layout/flow_layout_and_writing_modes)
- [Formatting Contexts Explained](css_flow_layout/intro_to_formatting_contexts)
- [In Flow and Out of Flow](css_flow_layout/in_flow_and_out_of_flow)

### display: flex

- [Basic concepts of flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)
- [Aligning Items in a Flex Container](css_flexible_box_layout/aligning_items_in_a_flex_container)
- [Controlling Ratios of Flex Items Along the Main Axis](css_flexible_box_layout/controlling_ratios_of_flex_items_along_the_main_ax)
- [Cross-browser Flexbox mixins](css_flexible_box_layout/backwards_compatibility_of_flexbox)
- [Mastering Wrapping of Flex Items](css_flexible_box_layout/mastering_wrapping_of_flex_items)
- [Ordering Flex Items](css_flexible_box_layout/ordering_flex_items)
- [Relationship of flexbox to other layout methods](css_flexible_box_layout/relationship_of_flexbox_to_other_layout_methods)
- [Backwards Compatibility of Flexbox](css_flexible_box_layout/backwards_compatibility_of_flexbox)
- [Typical use cases of Flexbox](css_flexible_box_layout/typical_use_cases_of_flexbox)

### display: grid

- [Basic Concepts of Grid Layout](css_grid_layout/basic_concepts_of_grid_layout)
- [Relationship to other layout methods](css_grid_layout/relationship_of_grid_layout)
- [Line-based placement](css_grid_layout/line-based_placement_with_css_grid)
- [Grid template areas](css_grid_layout/grid_template_areas)
- [Layout using named grid lines](css_grid_layout/layout_using_named_grid_lines)
- [Auto-placement in grid layout](css_grid_layout/auto-placement_in_css_grid_layout)
- [Box alignment in grid layout](css_grid_layout/box_alignment_in_css_grid_layout)
- [Grids, logical values and writing modes](css_grid_layout/css_grid_logical_values_and_writing_modes)
- [CSS Grid Layout and Accessibility](css_grid_layout/css_grid_layout_and_accessibility)
- [CSS Grid Layout and Progressive Enhancement](css_grid_layout/css_grid_and_progressive_enhancement)
- [Realizing common layouts using grids](css_grid_layout/realizing_common_layouts_using_css_grid_layout)

## Accessibility concerns

### display: none

Using a `display` value of `none` on an element will remove it from the [accessibility tree](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis). This will cause the element and all its descendant elements to no longer be announced by screen reading technology.

If you want to visually hide the element, a more accessible alternative is to use [a combination of properties](https://gomakethings.com/hidden-content-for-better-a11y/#hiding-the-link) to remove it visually from the screen but keep it parsable by assistive technology such as screen readers.

### display: contents

Current implementations in most browsers will remove from the [accessibility tree](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis) any element with a `display` value of `contents` (but descendants will remain). This will cause the element itself to no longer be announced by screen reading technology. This is incorrect behavior according to the [CSS specification](https://drafts.csswg.org/css-display/#valdef-display-contents).

- [More accessible markup with display: contents | Hidde de Vries](https://hiddedevries.nl/en/blog/2018-04-21-more-accessible-markup-with-display-contents)
- [Display: Contents Is Not a CSS Reset | Adrian Roselli](https://adrianroselli.com/2018/05/display-contents-is-not-a-css-reset.html)

### Tables

Changing the `display` value of a [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) element to `block`, `grid`, or `flex` will alter its representation in the [accessibility tree](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis). This will cause the table to no longer be announced properly by screen reading technology.

- [Short note on what CSS display properties do to table semantics — The Paciello Group](https://developer.paciellogroup.com/blog/2018/03/short-note-on-what-css-display-properties-do-to-table-semantics/)
- [Hidden content for better a11y | Go Make Things](https://gomakethings.com/hidden-content-for-better-a11y/)
- [MDN Understanding WCAG, Guideline 1.3 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.3_%e2%80%94_create_content_that_can_be_presented_in_different_ways)
- [Understanding Success Criterion 1.3.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>inline</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as the specified value, except for positioned and floating elements and the root element. In both cases the computed value may be a keyword other than the one specified.</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ <display-outside> || <display-inside> ] | <display-listitem> | <display-internal> | <display-box> | <display-legacy>where
    <display-outside> = block | inline | run-in
    <display-inside> = flow | flow-root | table | flex | grid | ruby
    <display-listitem> = <display-outside>? && [ flow | flow-root ]? && list-item
    <display-internal> = table-row-group | table-header-group | table-footer-group | table-row | table-cell | table-column-group | table-column | table-caption | ruby-base | ruby-text | ruby-base-container | ruby-text-container
    <display-box> = contents | none
    <display-legacy> = inline-block | inline-list-item | inline-table | inline-flex | inline-grid

## Examples

### display value comparison

In this example we have two block-level container elements, each one with three inline children. Below that, we have a select menu that allows you to apply different `display` values to the containers, allowing you to compare and contrast how the different values affect the element's layout, and that of their children.

We've included [`padding`](padding) and [`background-color`](background-color) on the containers and their children, so that it is easier to see the effect the display values are having.

**Note**: We've not included any of the modern two-value syntax, as support for that is still fairly limited.

#### HTML

    <article class="container">
      <span>First</span>
      <span>Second</span>
      <span>Third</span>
    </article>

    <article class="container">
      <span>First</span>
      <span>Second</span>
      <span>Third</span>
    </article>

    <div>
      <label for="display">Choose a display value:</label>
      <select id="display">
        <option selected>block</option>
        <option>inline</option>
        <option>inline-block</option>
        <option>none</option>
        <option>flex</option>
        <option>inline-flex</option>
        <option>grid</option>
        <option>inline-grid</option>
        <option>table</option>
        <option>list-item</option>
      </select>
    </div>

#### CSS

    html {
      font-family: helvetica, arial, sans-serif;
      letter-spacing: 1px;
      padding-top: 10px;
    }

    article {
      background-color: red;
    }

    article span {
      background-color: black;
      color: white;
      margin: 1px;
    }

    article, span {
      padding: 10px;
      border-radius: 7px;
    }

    article, div {
      margin: 20px;
    }

#### JavaScript

    const articles = document.querySelectorAll('.container');
    const select = document.querySelector('select');

    function updateDisplay() {
      articles.forEach((article) => {
        article.style.display = select.value;
      });
    }

    select.addEventListener('change', updateDisplay);

    updateDisplay();

#### Result

**Note**: You can find more examples in the pages for each separate display data type, linked above.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-display/#the-display-properties">CSS Display Module Level 3<br />
<span class="small">The definition of 'display' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added <code>run-in</code>, <code>flow</code>, <code>flow-root</code>, <code>contents</code>, and multi-keyword values.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-ruby/#ruby-display">CSS Ruby Layout Module Level 1<br />
<span class="small">The definition of 'display' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added <code>ruby</code>, <code>ruby-base</code>, <code>ruby-text</code>, <code>ruby-base-container</code>, and <code>ruby-text-container</code>.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid/#grid-containers">CSS Grid Layout<br />
<span class="small">The definition of 'display' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the grid box model values.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-flexbox-1/#flex-containers">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'display' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the flexible box model values.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/visuren.html#display-prop">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'display' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added the table model values and <code>inline-block.</code></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#display">CSS Level 1<br />
<span class="small">The definition of 'display' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition. Basic values: <code>none</code>, <code>block</code>, <code>inline</code>, and <code>list-item</code>.</td></tr></tbody></table>

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

`display`

1

12

1

4

7

1

≤37

18

4

10.1

1

1.0

`contents`

65

58-65

79

37

36-53

No

52

45-52

11.1

65

65

58-65

57

47

43-47

11.3

9.0

`display-outside`

1

12

1

4

7

1

1

18

4

10.1

1

1.0

`flex`

29

21

12

20

Firefox 28 added multi-line flexbox support.

11

IE incorrectly positions inline block content inside flex containers. See the [discussion on Microsoft Answers](https://answers.microsoft.com/en-us/ie/forum/ie11-iewindows_10/inline-block-content-in-a-flex-container-not/deea64e2-933b-4bd2-a98c-62be16d04b57).

8

IE incorrectly positions inline block content inside flex containers. See the [discussion on Microsoft Answers](https://answers.microsoft.com/en-us/ie/forum/ie11-iewindows_10/inline-block-content-in-a-flex-container-not/deea64e2-933b-4bd2-a98c-62be16d04b57).

16

15

12.1-15

9

6.1

4.4

≤37

29

25

20

Firefox 28 added multi-line flexbox support.

16

14

12.1-14

9

7

2.0

1.5

`flow-root`

58

79

53

No

45

13

58

58

53

43

13

7.0

`grid`

57

16

12

52

10

Internet Explorer implements an older version of the specification.

44

10.1

57

57

52

43

10.3

6.0

Samsung Internet added this earlier than the corresponding Chrome version would indicate.

`inline-block`

1

12

1

8

6

Until Internet Explorer 8, `inline-block` is only for natural inline elements.

7

1

≤37

18

4

14

1

1.0

`inline-flex`

29

21

12

20

Firefox 28 added multi-line flexbox support.

11

8

16

15

9

6.1

4.4

≤37

29

25

20

Firefox 28 added multi-line flexbox support.

16

14

9

6.1

2.0

1.5

`inline-grid`

57

16

12

52

10

Internet Explorer implements an older version of the specification.

44

10.1

57

57

52

43

10.3

6.0

Samsung Internet added this earlier than the corresponding Chrome version would indicate.

`inline-table`

1

12

3

8

7

1

≤37

18

4

14

1

1.0

`list-item`

1

12

1

6

7

1

≤37

18

4

14

1

1.0

`multi-keyword_values`

No

No

70

No

No

No

No

No

No

No

No

No

`none`

1

Chrome 65 stopped creating layout objects for elements inside an `<iframe>` with `display:none` applied.

12

1

4

7

Opera 52 stopped creating layout objects for elements inside an `<iframe>` with `display:none` applied.

1

≤37

WebView 65 stopped creating layout objects for elements inside an `<iframe>` with `display:none` applied.

18

Chrome 65 stopped creating layout objects for elements inside an `<iframe>` with `display:none` applied.

4

10.1

Opera Android 47 stopped creating layout objects for elements inside an `<iframe>` with `display:none` applied.

1

1.0

Chrome 65 stopped creating layout objects for elements inside an `<iframe>` with `display:none` applied.

`ruby_values`

No

12-79

38

7

No

No

No

No

38

No

No

No

`table_values`

1

12

1

8

7

1

≤37

18

4

14

1

1.0

`xul_box_values`

No

No

1-64

This is still available to Firefox UI code.

62

No

No

No

No

No

4-64

This is still available to Firefox UI code.

62

No

No

No

`xul_deck_values`

No

No

1-62

This is still available to Firefox UI code.

62

No

No

No

No

No

4-62

This is still available to Firefox UI code.

62

No

No

No

`xul_grid_values`

No

No

1-62

This is still available to Firefox UI code.

62

No

No

No

No

No

4-62

This is still available to Firefox UI code.

62

No

No

No

`xul_inline_grid_stack`

No

No

1-62

Available to Firefox UI code.

62-70

No

No

No

No

No

4-62

This is still available to Firefox UI code.

62

No

No

No

`xul_popup_values`

No

No

1-62

This is still available to Firefox UI code.

62

No

No

No

No

No

4-62

This is still available to Firefox UI code.

62

No

No

No

`xul_stack_value`

No

No

1-62

This is still available to Firefox UI code.

62

No

No

No

No

No

4-62

This is still available to Firefox UI code.

62

No

No

No

## See also

- [Block and inline layout in normal flow](css_flow_layout/block_and_inline_layout_in_normal_flow)
- [Introduction to formatting contexts](css_flow_layout/intro_to_formatting_contexts)
- [`visibility`](visibility), [`float`](float), [`position`](position)
- [`grid`](grid), [`flex`](flex)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/display" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/display</a>
