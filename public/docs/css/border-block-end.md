# border-block-end

The `border-block-end` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is a [shorthand property](shorthand_properties) for setting the individual logical block-end border property values in a single place in the style sheet.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`border-block-end-color`](border-block-end-color)
- [`border-block-end-style`](border-block-end-style)
- [`border-block-end-width`](border-block-end-width)

## Syntax

    border-block-end: 1px;
    border-block-end: 2px dotted;
    border-block-end: medium dashed blue;

`border-block-end` can be used to set the values for one or more of [`border-block-end-width`](border-block-end-width), [`border-block-end-style`](border-block-end-style), and [`border-block-end-color`](border-block-end-color). The physical border to which it maps depends on the element's writing mode, directionality, and text orientation. It corresponds to the [`border-top`](border-top), [`border-right`](border-right), [`border-bottom`](border-bottom), or [`border-left`](border-left) property depending on the values defined for [`writing-mode`](writing-mode), [`direction`](direction), and [`text-orientation`](text-orientation).

Related properties are [`border-block-start`](border-block-start), [`border-inline-start`](border-inline-start), and [`border-inline-end`](border-inline-end), which define the other borders of the element.

### Values

The `border-block-end` is specified with one or more of the following, in any order:

`<'border-width'>`  
The width of the border. See [`border-width`](border-width).

`<'border-style'>`  
The line style of the border. See [`border-style`](border-style).

`<'color'>`  
The color of the border. See [`color`](color).

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-width"><code>border-top-width</code></a>: <code>medium</code></li><li><a href="border-top-style"><code>border-top-style</code></a>: <code>none</code></li><li><a href="border-top-color"><code>border-top-color</code></a>: <code>currentcolor</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-width"><code>border-top-width</code></a>: the absolute length or <code>0</code> if <a href="border-top-style"><code>border-top-style</code></a> is <code>none</code> or <code>hidden</code></li><li><a href="border-top-style"><code>border-top-style</code></a>: as specified</li><li><a href="border-top-color"><code>border-top-color</code></a>: computed color</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-block-end-color"><code>border-block-end-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="border-block-end-style"><code>border-block-end-style</code></a>: discrete</li><li><a href="border-block-end-width"><code>border-block-end-width</code></a>: a <a href="length#interpolation">length</a></li></ul></td></tr></tbody></table>

## Formal syntax

    <'border-top-width'> || <'border-top-style'> || <color>where
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

## Examples

### Border with vertical text

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
      border-block-end: 5px dashed blue;
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-border-block-end">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'border-block-end' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-block-end`

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

- This property maps to one of the physical border properties: [`border-top`](border-top), [`border-right`](border-right), [`border-bottom`](border-bottom), or [`border-left`](border-left).
- [`writing-mode`](writing-mode), [`direction`](direction), [`text-orientation`](text-orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end</a>