# Layout and the containing block

The size and position of an element are often impacted by its **containing block**. Most often, the containing block is the [content area](css_box_model/introduction_to_the_css_box_model#content-area) of an element's nearest [block-level](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements) ancestor, but this is not always the case. In this article, we examine the factors that determine an element's containing block.

When a user agent (such as your browser) lays out a document, it generates a box for every element. Each box is divided into four areas:

1.  Content area
2.  Padding area
3.  Border area
4.  Margin area

<img src="data:image/png;base64,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" alt="Diagram of the box model" width="544" height="300" />

Many developers believe that the containing block of an element is always the content area of its parent, but that isn't necessarily true. Let's investigate the factors that determine what an element's containing block is.

## Effects of the containing block

Before learning what determines the containing block of an element, it's useful to know why it matters in the first place.

The size and position of an element are often impacted by its containing block. Percentage values that are applied to the [`width`](width), [`height`](height), [`padding`](padding), [`margin`](margin), and offset properties of an absolutely positioned element (i.e., which has its [`position`](position) set to `absolute` or `fixed`) are computed from the element's containing block.

## Identifying the containing block

The process for identifying the containing block depends entirely on the value of the element's [`position`](position) property:

1.  If the `position` property is `static`, `relative`, or `sticky`, the containing block is formed by the edge of the _content box_ of the nearest ancestor element that is either **a block container** (such as an inline-block, block, or list-item element) or **establishes a formatting context** (such as a table container, flex container, grid container, or the block container itself).
2.  If the `position` property is `absolute`, the containing block is formed by the edge of the _padding box_ of the nearest ancestor element that has a `position` value other than `static` (`fixed`, `absolute`, `relative`, or `sticky`).
3.  If the `position` property is `fixed`, the containing block is established by the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) (in the case of continuous media) or the page area (in the case of paged media).
4.  If the `position` property is `absolute` or `fixed`, the containing block may also be formed by the edge of the _padding box_ of the nearest ancestor element that has the following:
    1.  A [`transform`](transform) or [`perspective`](perspective) value other than `none`
    2.  A [`will-change`](will-change) value of `transform` or `perspective`
    3.  A [`filter`](filter) value other than `none` or a `will-change` value of `filter` (only works on Firefox).
    4.  A [`contain`](contain) value of `paint` (e.g. `contain: paint;`)

**Note:** The containing block in which the root element ([`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)) resides is a rectangle called the **initial containing block**. It has the dimensions of the viewport (for continuous media) or the page area (for paged media).

## Calculating percentage values from the containing block

As noted above, when certain properties are given a percentage value, the computed value depends on the element's containing block. The properties that work this way are **box model properties** and **offset properties**:

1.  The [`height`](height), [`top`](top), and [`bottom`](bottom) properties compute percentage values from the `height` of the containing block.
2.  The [`width`](width), [`left`](left), [`right`](right), [`padding`](padding), and [`margin`](margin) properties compute percentage values from the `width` of the containing block.

## Some examples

The HTML code for all our examples is:

    <body>
      <section>
        <p>This is a paragraph!</p>
      </section>
    </body>

Only the CSS is altered in each instance below.

### Example 1

In this example, the paragraph is statically positioned, so its containing block is [`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section) because it's the nearest ancestor that is a block container.

    body {
      background: beige;
    }

    section {
      display: block;
      width: 400px;
      height: 160px;
      background: lightgray;
    }

    p {
      width: 50%;   /* == 400px * .5 = 200px */
      height: 25%;  /* == 160px * .25 = 40px */
      margin: 5%;   /* == 400px * .05 = 20px */
      padding: 5%;  /* == 400px * .05 = 20px */
      background: cyan;
    }

### Example 2

In this example, the paragraph's containing block is the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) element, because `<section>` is not a block container (because of `display: inline`) and doesn’t establish a formatting context.

    body {
      background: beige;
    }

    section {
      display: inline;
      background: lightgray;
    }

    p {
      width: 50%;     /* == half the body's width */
      height: 200px;  /* Note: a percentage would be 0 */
      background: cyan;
    }

### Example 3

In this example, the paragraph's containing block is `<section>` because the latter's `position` is `absolute`. The paragraph's percentage values are affected by the `padding` of its containing block, though if the containing block's [`box-sizing`](box-sizing) value were `border-box` this would not be the case.

    body {
      background: beige;
    }

    section {
      position: absolute;
      left: 30px;
      top: 30px;
      width: 400px;
      height: 160px;
      padding: 30px 20px;
      background: lightgray;
    }

    p {
      position: absolute;
      width: 50%;   /* == (400px + 20px + 20px) * .5 = 220px */
      height: 25%;  /* == (160px + 30px + 30px) * .25 = 55px */
      margin: 5%;   /* == (400px + 20px + 20px) * .05 = 22px */
      padding: 5%;  /* == (400px + 20px + 20px) * .05 = 22px */
      background: cyan;
    }

### Example 4

In this example, the paragraph's `position` is `fixed`, so its containing block is the initial containing block (on screens, the viewport). Thus, the paragraph's dimensions change based on the size of the browser window.

    body {
      background: beige;
    }

    section {
      width: 400px;
      height: 480px;
      margin: 30px;
      padding: 15px;
      background: lightgray;
    }

    p {
      position: fixed;
      width: 50%;   /* == (50vw - (width of vertical scrollbar)) */
      height: 50%;  /* == (50vh - (height of horizontal scrollbar)) */
      margin: 5%;   /* == (5vw - (width of vertical scrollbar)) */
      padding: 5%;  /* == (5vw - (width of vertical scrollbar)) */
      background: cyan;
    }

### Example 5

In this example, the paragraph's `position` is `absolute`, so its containing block is `<section>`, which is the nearest ancestor with a [`transform`](transform) property that isn't `none`.

    body {
      background: beige;
    }

    section {
      transform: rotate(0deg);
      width: 400px;
      height: 160px;
      background: lightgray;
    }

    p {
      position: absolute;
      left: 80px;
      top: 30px;
      width: 50%;   /* == 200px */
      height: 25%;  /* == 40px */
      margin: 5%;   /* == 20px */
      padding: 5%;  /* == 20px */
      background: cyan;
    }

## See also

- CSS Key Concepts: [CSS syntax](syntax), [at-rule](at-rule), [comments](comments), [specificity](specificity) and [inheritance](inheritance), the [box](css_box_model/introduction_to_the_css_box_model), [layout modes](layout_mode) and [visual formatting models](visual_formatting_model), and [margin collapsing](css_box_model/mastering_margin_collapsing), or the [initial](initial_value), [computed](computed_value), [resolved](resolved_value), [specified](specified_value), [used](used_value), and [actual](actual_value) values. Definitions of [value syntax](value_definition_syntax), [shorthand properties](shorthand_properties) and [replaced elements](replaced_element).
- The [`all`](all) property resets all CSS declarations to a given known state

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_block" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_block</a>
