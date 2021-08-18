# margin-inline

The `margin-inline` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](shorthand_properties) is a shorthand property that defines both the logical inline start and end margins of an element, which maps to physical margins depending on the element's writing mode, directionality, and text orientation.

    /* <length> values */
    margin-inline: 10px 20px;  /* An absolute length */
    margin-inline: 1em 2em;    /* relative to the text size */
    margin-inline: 5% 2%;      /* relative to the nearest block container's width */
    margin-inline: 10px;       /* sets both start and end values */

    /* Keyword values */
    margin-inline: auto;

    /* Global values */
    margin-inline: inherit;
    margin-inline: initial;
    margin-inline: unset;

This property corresponds to the [`margin-top`](margin-top) and [`margin-bottom`](margin-bottom), or the [`margin-right`](margin-right) and [`margin-left`](margin-left) properties, depending on the values defined for [`writing-mode`](writing-mode), [`direction`](direction), and [`text-orientation`](text-orientation).

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`margin-inline-start`](margin-inline-start)
- [`margin-inline-end`](margin-inline-end)

If 2 values are specified, the first value sets the start, the second value sets the end. If 1 value is specified, it sets both properties with the same value.

## Syntax

### Values

The `margin-inline` property takes the same values as the [`margin-left`](margin-left) property.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>same as <a href="margin"><code>margin</code></a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>depends on layout model</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>if specified as a length, the corresponding absolute length; if specified as a percentage, the specified value; otherwise, <code>auto</code></td></tr><tr class="even"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <'margin-left'>{1,2}

## Examples

### Setting inline start and end margins

#### CSS

    div {
      background-color: yellow;
      width: 120px;
      height: auto;
      border: 1px solid green;
    }

    p {
      margin: 0;
      margin-inline: 20px 40px;
      background-color: tan;
    }

    .verticalExample {
      writing-mode: vertical-rl;
    }

#### HTML

    <div>
      <p>Example text</p>
    </div>
    <div class="verticalExample">
      <p>Example text</p>
    </div>

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-margin-inline">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'margin-inline' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>same as <a href="margin"><code>margin</code></a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>depends on layout model</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>if specified as a length, the corresponding absolute length; if specified as a percentage, the specified value; otherwise, <code>auto</code></td></tr><tr class="even"><td>Animation type</td><td>discrete</td></tr></tbody></table>

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

`margin-inline`

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

- The mapped physical properties: [`margin-top`](margin-top), [`margin-right`](margin-right), [`margin-bottom`](margin-bottom), and [`margin-left`](margin-left)
- [`writing-mode`](writing-mode), [`direction`](direction), [`text-orientation`](text-orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline</a>
