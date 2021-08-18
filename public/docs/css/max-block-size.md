# max-block-size

The `max-block-size` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the maximum size of an element in the direction opposite that of the writing direction as specified by [`writing-mode`](writing-mode). That is, if the writing direction is horizontal, then `max-block-size` is equivalent to [`max-height`](max-height); if the writing direction is vertical, `max-block-size` is the same as [`max-width`](max-width).

The other dimension's maximum length is specified using the [`max-inline-size`](max-inline-size) property.

This is useful because the `max-width` is always used for horizontal sizes and `max-height` is always used for vertical sizes, and if you need to set lengths based on the size of your text content, you need to be able to do so with the writing direction in mind.

Any time you would normally use `max-height` or `max-width`, you should instead use `max-block-size` to set the maximum "height" of the content (even though this may not be a vertical value) and `max-inline-size` to set the maximum "width" of the content (although this may instead be vertical rather than horizontal). See the [Example](writing-mode#example) in [writing-mode](writing-mode), which shows the different writing modes in action.

## Syntax

    /* <length> values */
    max-block-size: 300px;
    max-block-size: 25em;

    /* <percentage> values */
    max-block-size: 75%;

    /* Keyword values */
    max-block-size: auto;
    max-block-size: max-content;
    max-block-size: min-content;
    max-block-size: fit-content(20em);

    /* Global values */
    max-block-size: inherit;
    max-block-size: initial;
    max-block-size: unset;

### Values

The `max-block-size` property's value can be any value that's legal for the [`max-width`](max-width) and [`max-height`](max-height) properties:

[`<length>`](length)  
Defines the `max-width` as an absolute value.

[`<percentage>`](percentage)  
Defines the `max-width` as a percentage of the containing block's width.

`none`  
No limit on the size of the box.

`max-content`  
The intrinsic preferred `max-width`.

`min-content`  
The intrinsic minimum `max-width`.

`fit-content(<length-percentage>`)  
Uses the `fit-content` formula with the available space replaced by the specified argument, i.e. `min(max-content, max(min-content, argument))`.

### How writing-mode affects directionality

The values of `writing-mode` affect the mapping of `max-block-size` to `max-width` or `max-height` as follows:

<table><thead><tr class="header"><th>Values of <code>writing-mode</code></th><th><code>max-block-size</code> is equivalent to</th></tr></thead><tbody><tr class="odd"><td><code>horizontal-tb</code>, <code>lr</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span>, <code>lr-tb</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span>, <code>rl</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span>, <code>rb</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span>, <code>rb-rl</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><a href="max-height"><code>max-height</code></a></td></tr><tr class="even"><td><code>vertical-rl</code>, <code>vertical-lr</code>, <code>sideways-rl</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span>, <code>sideways-lr</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span>, <code>tb</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span>, <code>tb-rl</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><a href="max-width"><code>max-width</code></a></td></tr></tbody></table>

The `writing-mode` values `sideways-lr` and `sideways-rl` were removed from the CSS Writing Modes Level 3 specification late in its design process. They may be restored in Level 4.

The writing modes `lr`, `lr-tb`, `rl`, `rb`, and `rb-tl` are no longer allowed in [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) contexts; they may only be used in [SVG](https://developer.mozilla.org/en-US/docs/Glossary/SVG) 1.x contexts.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>same as <a href="width"><code>width</code></a> and <a href="height"><code>height</code></a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>block-size of containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>same as <a href="max-width"><code>max-width</code></a> and <a href="max-height"><code>max-height</code></a></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <'max-width'>

## Examples

### Setting max-block-size with horizontal and vertical text

In this example, the same text (the opening sentences from [Herman Melville's](https://en.wikipedia.org/wiki/Herman_Melville) novel _[Moby-Dick](https://en.wikipedia.org/wiki/Moby-Dick)_) is presented in both the `horizontal-tb` and `vertical-rl` writing modes.

Everything else about the two boxes is identical, including the values used for [`max-block-size`](max-block-size).

#### HTML

The HTML establishes the two [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) blocks that will be presented with their [`writing-mode`](writing-mode) set using the classes `horizontal` or `vertical`. Both boxes share the `standard-box` class, which establishes coloring, padding, and their respective values of `max-block-size`.

    <p>Writing mode <code>horizontal-tb</code> (the default):</p>
    <div class="standard-box horizontal">
      Call me Ishmael. Some years ago—never mind how
      long precisely—having little or no money in my
      purse, and nothing particular to interest me on
      shore, I thought I would sail about a little and see
      the watery part of the world. It is a way I have of
      driving off the spleen and regulating the
      circulation.
    </div>

    <p>Writing mode <code>vertical-rl</code>:</p>
    <div class="standard-box vertical">
      Call me Ishmael. Some years ago—never mind how
      long precisely—having little or no money in my
      purse, and nothing particular to interest me on
      shore, I thought I would sail about a little and see
      the watery part of the world. It is a way I have of
      driving off the spleen and regulating the
      circulation.
    </div>

#### CSS

The CSS defines three classes. The first, `standard-box`, is applied to both boxes, as seen above. It provides standard styling including the minimum and maximum block sizes, font size, and so forth.

After that come the classes `horizontal` and `vertical`, which add the [`writing-mode`](writing-mode) property to the box, with the value set to `horizontal-tb` or `vertical-rl` depending on which class is used.

    .standard-box {
      padding: 4px;
      background-color: #abcdef;
      color: #000;
      font: 16px "Open Sans", "Helvetica", "Arial", sans-serif;
      max-block-size: 160px;
      min-block-size: 100px;
    }

    .horizontal {
      writing-mode: horizontal-tb;
    }

    .vertical {
      writing-mode: vertical-rl;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-max-block-size">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'max-block-size' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`max-block-size`

57

79

41

No

44

12.1

57

57

41

43

12.2

5.0

`fit-content`

57

79

No

No

44

12.1

57

57

No

43

12.2

5.0

`max-content`

57

79

66

41

No

44

12.1

57

57

66

41

43

12.2

5.0

`min-content`

57

79

66

41

No

44

12.1

57

57

66

41

43

12.2

5.0

## See also

- The mapped physical properties: [`max-width`](max-width) and [`max-height`](max-height)
- Setting the other direction's maximum size: [`max-inline-size`](max-inline-size)
- [`writing-mode`](writing-mode)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/max-block-size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/max-block-size</a>
