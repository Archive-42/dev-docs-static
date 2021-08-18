# padding-inline-end

The `padding-inline-end` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the logical inline end padding of an element, which maps to a physical padding depending on the element's writing mode, directionality, and text orientation.

## Syntax

    /* <length> values */
    padding-inline-end: 10px;     /* An absolute length */
    padding-inline-end: 1em;      /* A length relative to the text size */

    /* <percentage> value */
    padding-inline-end: 5%;       /* A padding relative to the block container's width */

    /* Global values */
    padding-inline-end: inherit;
    padding-inline-end: initial;
    padding-inline-end: unset;

### Values

The `padding-inline-end` property takes the same values as the [`padding-left`](padding-left) property.

## Description

This property corresponds to the [`padding-top`](padding-top), [`padding-right`](padding-right), [`padding-bottom`](padding-bottom), or [`padding-left`](padding-left) property depending on the values defined for [`writing-mode`](writing-mode), [`direction`](direction), and [`text-orientation`](text-orientation).

It relates to [`padding-block-start`](padding-block-start), [`padding-block-end`](padding-block-end), and [`padding-inline-start`](padding-inline-start), which define the other paddings of the element.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>logical-width of containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as <a href="length"><code>&lt;length&gt;</code></a></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <'padding-left'>

## Examples

### Setting inline end padding for vertical text

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
      padding-inline-end: 20px;
      background-color: #C8C800;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-padding-inline-end">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'padding-inline-end' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`padding-inline-end`

69

2

79

79

41

3

No

56

15

12.1

3

69

2

69

18

41

4

48

14

12.2

3

10.0

1.0

## See also

- The mapped physical properties: [`padding-top`](padding-top), [`padding-right`](padding-right), [`padding-bottom`](padding-bottom), and [`padding-left`](padding-left)
- [`writing-mode`](writing-mode), [`direction`](direction), [`text-orientation`](text-orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-end" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-end</a>
