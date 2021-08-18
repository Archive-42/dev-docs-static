# position

The `position` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how an element is positioned in a document. The [`top`](top), [`right`](right), [`bottom`](bottom), and [`left`](left) properties determine the final location of positioned elements.

## Syntax

The `position` property is specified as a single keyword chosen from the list of values below.

### Values

`static`  
The element is positioned according to the normal flow of the document. The [`top`](top), [`right`](right), [`bottom`](bottom), [`left`](left), and [`z-index`](z-index) properties have _no effect_. This is the default value.

`relative`  
The element is positioned according to the normal flow of the document, and then offset _relative to itself_ based on the values of `top`, `right`, `bottom`, and `left`. The offset does not affect the position of any other elements; thus, the space given for the element in the page layout is the same as if position were `static`.

This value creates a new [stacking context](css_positioning/understanding_z_index/the_stacking_context) when the value of `z-index` is not `auto`. Its effect on `table-*-group`, `table-row`, `table-column`, `table-cell`, and `table-caption` elements is undefined.

`absolute`  
The element is removed from the normal document flow, and no space is created for the element in the page layout. It is positioned relative to its closest positioned ancestor, if any; otherwise, it is placed relative to the initial [containing block](containing_block). Its final position is determined by the values of `top`, `right`, `bottom`, and `left`.

This value creates a new [stacking context](css_positioning/understanding_z_index/the_stacking_context) when the value of `z-index` is not `auto`. The margins of absolutely positioned boxes do not [collapse](css_box_model/mastering_margin_collapsing) with other margins.

`fixed`  
The element is removed from the normal document flow, and no space is created for the element in the page layout. It is positioned relative to the initial [containing block](containing_block) established by the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport), except when one of its ancestors has a `transform`, `perspective`, or `filter` property set to something other than `none` (see the [CSS Transforms Spec](https://www.w3.org/TR/css-transforms-1/#propdef-transform)), in which case that ancestor behaves as the containing block. (Note that there are browser inconsistencies with `perspective` and `filter` contributing to containing block formation.) Its final position is determined by the values of `top`, `right`, `bottom`, and `left`.

This value always creates a new [stacking context](css_positioning/understanding_z_index/the_stacking_context). In printed documents, the element is placed in the same position on _every page_.

`sticky`  
The element is positioned according to the normal flow of the document, and then offset relative to its _nearest scrolling ancestor_ and [containing block](containing_block) (nearest block-level ancestor), including table-related elements, based on the values of `top`, `right`, `bottom`, and `left`. The offset does not affect the position of any other elements.

This value always creates a new [stacking context](css_positioning/understanding_z_index/the_stacking_context). Note that a sticky element "sticks" to its nearest ancestor that has a "scrolling mechanism" (created when `overflow` is `hidden`, `scroll`, `auto`, or `overlay`), even if that ancestor isn't the nearest actually scrolling ancestor. This effectively inhibits any "sticky" behavior (see the [GitHub issue on W3C CSSWG](https://github.com/w3c/csswg-drafts/issues/865)).

## Description

### Types of positioning

- A **positioned element** is an element whose [computed](computed_value) `position` value is either `relative`, `absolute`, `fixed`, or `sticky`. (In other words, it's anything except `static`.)
- A **relatively positioned element** is an element whose [computed](computed_value) `position` value is `relative`. The [`top`](top) and [`bottom`](bottom) properties specify the vertical offset from its normal position; the [`left`](left) and [`right`](right) properties specify the horizontal offset.
- An **absolutely positioned element** is an element whose [computed](computed_value) `position` value is `absolute` or `fixed`. The [`top`](top), [`right`](right), [`bottom`](bottom), and [`left`](left) properties specify offsets from the edges of the element's [containing block](containing_block). (The containing block is the ancestor relative to which the element is positioned.) If the element has margins, they are added to the offset. The element establishes a new [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context) (BFC) for its contents.
- A **stickily positioned element** is an element whose [computed](computed_value) `position` value is `sticky`. It's treated as relatively positioned until its [containing block](containing_block) crosses a specified threshold (such as setting [`top`](top) to value other than auto) within its flow root (or the container it scrolls within), at which point it is treated as "stuck" until meeting the opposite edge of its [containing block](containing_block).

Most of the time, absolutely positioned elements that have [`height`](height) and [`width`](width) set to `auto` are sized so as to fit their contents. However, non-[replaced](replaced_element), absolutely positioned elements can be made to fill the available vertical space by specifying both [`top`](top) and [`bottom`](bottom) and leaving [`height`](height) unspecified (that is, `auto`). They can likewise be made to fill the available horizontal space by specifying both [`left`](left) and [`right`](right) and leaving [`width`](width) as `auto`.

Except for the case just described (of absolutely positioned elements filling the available space):

- If both `top` and `bottom` are specified (technically, not `auto`), `top` wins.
- If both `left` and `right` are specified, `left` wins when [`direction`](direction) is `ltr` (English, horizontal Japanese, etc.) and `right` wins when [`direction`](direction) is `rtl` (Persian, Arabic, Hebrew, etc.).

## Accessibility concerns

Ensure that elements positioned with an `absolute` or `fixed` value do not obscure other content when the page is zoomed to increase text size.

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Visual Presentation: Understanding SC 1.4.8 | Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html)

### Performance & Accessibility

Scrolling elements containing `fixed` or `sticky` content can cause performance and accessibility issues. As a user scrolls, the browser must repaint the sticky or fixed content in a new location. Depending on the content needing to be repainted, the browser performance, and the device's processing speed, the browser may not be able to manage repaints at 60 fps, causing accessibility concerns for people with sensitivities and jank for everyone. One solution is to add [`will-change: transform`](will-change) to the positioned elements to render the element in its own layer, improving repaint speed and therefore improving performance and accessibility.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>static</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr><tr class="even"><td>Creates <a href="css_positioning/understanding_z_index/the_stacking_context">stacking context</a></td><td>yes</td></tr></tbody></table>

## Formal syntax

    static | relative | absolute | sticky | fixed

## Examples

### Relative positioning

Relatively positioned elements are offset a given amount from their normal position within the document, but without the offset affecting other elements. In the example below, note how the other elements are placed as if "Two" were taking up the space of its normal location.

#### HTML

    <div class="box" id="one">One</div>
    <div class="box" id="two">Two</div>
    <div class="box" id="three">Three</div>
    <div class="box" id="four">Four</div>

#### CSS

    * {
      box-sizing: border-box;
    }

    .box {
      display: inline-block;
      width: 100px;
      height: 100px;
      background: red;
      color: white;
    }

    #two {
      position: relative;
      top: 20px;
      left: 20px;
      background: blue;
    }

### Absolute positioning

Elements that are relatively positioned remain in the normal flow of the document. In contrast, an element that is absolutely positioned is taken out of the flow; thus, other elements are positioned as if it did not exist. The absolutely positioned element is positioned relative to its _nearest positioned ancestor_ (i.e., the nearest ancestor that is not `static`). If a positioned ancestor doesn't exist, it is positioned relative to the ICB (initial containing block — see also the [W3C definition](https://www.w3.org/TR/CSS2/visudet.html#containing-block-details)), which is the containing block of the document's root element.

#### HTML

    <h1>Absolute positioning</h1>

    <p>I am a basic block level element. My adjacent block level elements sit on new lines below me.</p>

    <p class="positioned">By default we span 100% of the width of our parent element, and we are as tall as our child content. Our total width and height is our content + padding + border width/height.</p>

    <p>We are separated by our margins. Because of margin collapsing, we are separated by the width of one of our margins, not both.</p>

    <p>inline elements <span>like this one</span> and <span>this one</span> sit on the same line as one another, and adjacent text nodes, if there is space on the same line. Overflowing inline elements <span>wrap onto a new line if possible — like this one containing text</span>, or just go on to a new line if not, much like this image will do: <img src="https://mdn.mozillademos.org/files/13360/long.jpg"></p>

#### CSS

    * {
      box-sizing: border-box;
    }

    body {
      width: 500px;
      margin: 0 auto;
    }

    p {
      background: aqua;
      border: 3px solid blue;
      padding: 10px;
      margin: 10px;
    }

    span {
      background: red;
      border: 1px solid black;
    }

    .positioned {
      position: absolute;
      background: yellow;
      top: 30px;
      left: 30px;
    }

#### Result

### Fixed positioning

Fixed positioning is similar to absolute positioning, with the exception that the element's [containing block](containing_block) is the initial containing block established by the _viewport_, unless any ancestor has `transform`, `perspective`, or `filter` property set to something other than `none` (see [CSS Transforms Spec](https://www.w3.org/TR/css-transforms-1/#propdef-transform)), which then causes that ancestor to take the place of the elements [containing block](containing_block). This can be used to create a "floating" element that stays in the same position regardless of scrolling. In the example below, box "One" is fixed at 80 pixels from the top of the page and 10 pixels from the left. Even after scrolling, it remains in the same place relative to the viewport.

#### HTML

    <div class="outer">
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam congue tortor eget pulvinar lobortis.
        Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Nam ac dolor augue.
        Pellentesque mi mi, laoreet et dolor sit amet, ultrices varius risus. Nam vitae iaculis elit.
        Aliquam mollis interdum libero. Sed sodales placerat egestas. Vestibulum ut arcu aliquam purus viverra dictum vel sit amet mi.
        Duis nisl mauris, aliquam sit amet luctus eget, dapibus in enim. Sed velit augue, pretium a sem aliquam, congue porttitor tortor.
        Sed tempor nisl a lorem consequat, id maximus erat aliquet. Sed sagittis porta libero sed condimentum.
        Aliquam finibus lectus nec ante congue rutrum. Curabitur quam quam, accumsan id ultrices ultrices, tempor et tellus.
      </p>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam congue tortor eget pulvinar lobortis.
        Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Nam ac dolor augue.
        Pellentesque mi mi, laoreet et dolor sit amet, ultrices varius risus. Nam vitae iaculis elit.
        Aliquam mollis interdum libero. Sed sodales placerat egestas. Vestibulum ut arcu aliquam purus viverra dictum vel sit amet mi.
        Duis nisl mauris, aliquam sit amet luctus eget, dapibus in enim. Sed velit augue, pretium a sem aliquam, congue porttitor tortor.
        Sed tempor nisl a lorem consequat, id maximus erat aliquet. Sed sagittis porta libero sed condimentum.
        Aliquam finibus lectus nec ante congue rutrum. Curabitur quam quam, accumsan id ultrices ultrices, tempor et tellus.
      </p>
      <div class="box" id="one">One</div>
    </div>

#### CSS

    * {
      box-sizing: border-box;
    }

    .box {
      width: 100px;
      height: 100px;
      background: red;
      color: white;
    }

    #one {
      position: fixed;
      top: 80px;
      left: 10px;
      background: blue;
    }

    .outer {
      width: 500px;
      height: 300px;
      overflow: scroll;
      padding-left: 150px;
    }

#### Result

### Sticky positioning

Sticky positioning can be thought of as a hybrid of relative and fixed positioning. A stickily positioned element is treated as relatively positioned until it crosses a specified threshold, at which point it is treated as fixed until it reaches the boundary of its parent. For instance...

    #one { position: sticky; top: 10px; }

...would position the element with id _one_ relatively until the viewport were scrolled such that the element would be less than 10 pixels from the top. Beyond that threshold, the element would be fixed to 10 pixels from the top.

A common use for sticky positioning is for the headings in an alphabetized list. The "B" heading will appear just below the items that begin with "A" until they are scrolled offscreen. Rather than sliding offscreen with the rest of the content, the "B" heading will then remain fixed to the top of the viewport until all the "B" items have scrolled offscreen, at which point it will be covered up by the "C" heading, and so on.

You must specify a threshold with at least one of `top`, `right`, `bottom`, or `left` for sticky positioning to behave as expected. Otherwise, it will be indistinguishable from relative positioning.

#### HTML

    <dl>
      <div>
        <dt>A</dt>
        <dd>Andrew W.K.</dd>
        <dd>Apparat</dd>
        <dd>Arcade Fire</dd>
        <dd>At The Drive-In</dd>
        <dd>Aziz Ansari</dd>
      </div>
      <div>
        <dt>C</dt>
        <dd>Chromeo</dd>
        <dd>Common</dd>
        <dd>Converge</dd>
        <dd>Crystal Castles</dd>
        <dd>Cursive</dd>
      </div>
      <div>
        <dt>E</dt>
        <dd>Explosions In The Sky</dd>
      </div>
      <div>
        <dt>T</dt>
        <dd>Ted Leo &amp; The Pharmacists</dd>
        <dd>T-Pain</dd>
        <dd>Thrice</dd>
        <dd>TV On The Radio</dd>
        <dd>Two Gallants</dd>
      </div>
    </dl>

#### CSS

    * {
      box-sizing: border-box;
    }

    dl > div {
      background: #FFF;
      padding: 24px 0 0 0;
    }

    dt {
      background: #B8C1C8;
      border-bottom: 1px solid #989EA4;
      border-top: 1px solid #717D85;
      color: #FFF;
      font: bold 18px/21px Helvetica, Arial, sans-serif;
      margin: 0;
      padding: 2px 0 0 12px;
      position: -webkit-sticky;
      position: sticky;
      top: -1px;
    }

    dd {
      font: bold 20px/45px Helvetica, Arial, sans-serif;
      margin: 0;
      padding: 0 0 0 12px;
      white-space: nowrap;
    }

    dd + dd {
      border-top: 1px solid #CCC;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/visuren.html#propdef-position">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'position' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-position-3/#position-property">CSS Positioned Layout Module Level 3<br />
<span class="small">The definition of 'position' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <code>sticky</code> property value.</td></tr></tbody></table>

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

`position`

1

12

1

\["Before Firefox 57, absolute positioning did not work correctly when applied to elements inside tables that have [`border-collapse`](https://developer.mozilla.org/docs/Web/CSS/border-collapse) applied to them ([bug 1379306](https://bugzil.la/1379306)).", "Before Firefox 30, absolute positioning of table rows and row groups was not supported ([bug 63895](https://bugzil.la/63895))."\]

4

4

1

≤37

18

4

\["Before Firefox 57, absolute positioning did not work correctly when applied to elements inside tables that have [`border-collapse`](https://developer.mozilla.org/docs/Web/CSS/border-collapse) applied to them ([bug 1379306](https://bugzil.la/1379306)).", "Before Firefox 30, absolute positioning of table rows and row groups was not supported ([bug 63895](https://bugzil.la/63895))."\]

14

1

1.0

`absolutely_positioned_flex_children`

52

12

52

10

39

11

52

52

52

41

11

6.0

`fixed`

1

12

1

Before Firefox 44, `position: fixed` didn't create a stacking context in most cases. Firefox and the specification have been modified to mimic Chrome and Safari's long-time behavior.

7

In Internet Explorer, fixed positioning doesn't work if the document is in [quirks mode](https://developer.mozilla.org/docs/Web/HTML/Quirks_Mode_and_Standards_Mode).

4

1

≤37

18

4

Before Firefox 44, `position: fixed` didn't create a stacking context in most cases. Firefox and the specification have been modified to mimic Chrome and Safari's long-time behavior.

14

1

1.0

`position_sticky_table_elements`

56

16

59

No

43

8

56

56

59

43

8

6.0

`sticky`

56

16

32

No

43

13

6.1

56

56

32

43

13

6.1

6.0

## See also

- [Learn CSS: Positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/position" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/position</a>
