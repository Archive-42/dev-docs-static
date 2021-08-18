# padding-block-end

The `padding-block-end` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the logical block end padding of an element, which maps to a physical padding depending on the element's writing mode, directionality, and text orientation.

## Syntax

    /* <length> values */
    padding-block-end: 10px;      /* An absolute length */
    padding-block-end: 1em;       /* A length relative to the text size */

    /* <percentage> value */
    padding-block-end: 5%;        /* A padding relative to the block container's width */

    /* Global values */
    padding-block-end: inherit;
    padding-block-end: initial;
    padding-block-end: unset;

### Values

The `padding-block-end` property takes the same values as the [`padding-left`](padding-left) property.

## Description

This property corresponds to the [`padding-top`](padding-top), [`padding-right`](padding-right), [`padding-bottom`](padding-bottom), or [`padding-left`](padding-left) property depending on the values defined for [`writing-mode`](writing-mode), [`direction`](direction), and [`text-orientation`](text-orientation).

It relates to [`padding-block-start`](padding-block-start), [`padding-inline-start`](padding-inline-start), and [`padding-inline-end`](padding-inline-end), which define the other paddings of the element.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>logical-width of containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as <a href="length"><code>&lt;length&gt;</code></a></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <'padding-left'>

## Examples

### Setting block end padding for vertical text

#### HTML

    <div>
      <p class="exampleText">Example text</p>
    </div>

#### CSS

    div {
      background-color: yellow;
      width: 120px;
      height: 120px;
    }

    .exampleText {
      writing-mode: vertical-lr;
      padding-block-end: 20px;
      background-color: #C8C800;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-padding-block-end">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'padding-block-end' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`padding-block-end`

69

79

41

No

56

12.1

69

69

41

48

12.2

10.0

## See also

- The mapped physical properties: [`padding-top`](padding-top), [`padding-right`](padding-right), [`padding-bottom`](padding-bottom), and [`padding-left`](padding-left)
- [`writing-mode`](writing-mode), [`direction`](direction), [`text-orientation`](text-orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block-end" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block-end</a>
