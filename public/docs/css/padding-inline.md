# padding-inline

The `padding-inline` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](shorthand_properties) defines the logical inline start and end padding of an element, which maps to physical padding properties depending on the element's writing mode, directionality, and text orientation.

    /* <length> values */
    padding-inline: 10px 20px;  /* An absolute length */
    padding-inline: 1em 2em;   /* relative to the text size */
    padding-inline: 10px; /* sets both start and end values */

    /* <percentage> values */
    padding-inline: 5% 2%; /* relative to the nearest block container's width */

    /* Global values */
    padding-inline: inherit;
    padding-inline: initial;
    padding-inline: unset;

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`padding-inline-end`](padding-inline-end)
- [`padding-inline-start`](padding-inline-start)

## Syntax

### Values

The `padding-inline` property takes the same values as the [`padding-left`](padding-left) property.

## Description

Values for this property correspond to the [`padding-top`](padding-top) and [`padding-bottom`](padding-bottom), or [`padding-right`](padding-right), and [`padding-left`](padding-left) property depending on the values defined for [`writing-mode`](writing-mode), [`direction`](direction), and [`text-orientation`](text-orientation).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>logical-width of containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as <a href="length"><code>&lt;length&gt;</code></a></td></tr><tr class="even"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <'padding-left'>{1,2}

## Examples

### Setting inline padding for vertical text

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
      writing-mode: vertical-rl;
      padding-inline: 20px 40px;
      background-color: #c8c800;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-padding-inline">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'padding-inline' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`padding-inline`

87

69

79

66

No

73

56

14.1

87

87

69

66

48

14.5

No

## See also

- The mapped physical properties: [`padding-top`](padding-top), [`padding-right`](padding-right), [`padding-bottom`](padding-bottom), and [`padding-left`](padding-left)
- [`writing-mode`](writing-mode), [`direction`](direction), [`text-orientation`](text-orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline</a>
