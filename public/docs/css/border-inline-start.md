# border-inline-start

The `border-inline-start` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is a [shorthand property](shorthand_properties) for setting the individual logical inline-start border property values in a single place in the style sheet.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`border-inline-start-color`](border-inline-start-color)
- [`border-inline-start-style`](border-inline-start-style)
- [`border-inline-start-width`](border-inline-start-width)

## Syntax

    border-inline-start: 1px;
    border-inline-start: 2px dotted;
    border-inline-start: medium dashed green;

The physical border to which `border-inline-start` maps depends on the element's writing mode, directionality, and text orientation. It corresponds to the [`border-top`](border-top), [`border-right`](border-right), [`border-bottom`](border-bottom), or [`border-left`](border-left) property depending on the values defined for [`writing-mode`](writing-mode), [`direction`](direction), and [`text-orientation`](text-orientation).

Related properties are [`border-block-start`](border-block-start), [`border-block-end`](border-block-end), and [`border-inline-end`](border-inline-end), which define the other borders of the element.

### Values

The `border-inline-start` is specified with one or more of the following, in any order:

`<'border-width'>`  
The width of the border. See [`border-width`](border-width).

`<'border-style'>`  
The line style of the border. See [`border-style`](border-style).

`<'color'>`  
The color of the border. See [`color`](color).

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-width"><code>border-width</code></a>: as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-width"><code>border-top-width</code></a>: <code>medium</code></li><li><a href="border-right-width"><code>border-right-width</code></a>: <code>medium</code></li><li><a href="border-bottom-width"><code>border-bottom-width</code></a>: <code>medium</code></li><li><a href="border-left-width"><code>border-left-width</code></a>: <code>medium</code></li></ul></li><li><a href="border-style"><code>border-style</code></a>: as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-style"><code>border-top-style</code></a>: <code>none</code></li><li><a href="border-right-style"><code>border-right-style</code></a>: <code>none</code></li><li><a href="border-bottom-style"><code>border-bottom-style</code></a>: <code>none</code></li><li><a href="border-left-style"><code>border-left-style</code></a>: <code>none</code></li></ul></li><li><a href="color"><code>color</code></a>: Varies from one browser to another</li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-width"><code>border-width</code></a>: as each of the properties of the shorthand:<br />
<ul><li><a href="border-bottom-width"><code>border-bottom-width</code></a>: the absolute length or <code>0</code> if <a href="border-bottom-style"><code>border-bottom-style</code></a> is <code>none</code> or <code>hidden</code></li><li><a href="border-left-width"><code>border-left-width</code></a>: the absolute length or <code>0</code> if <a href="border-left-style"><code>border-left-style</code></a> is <code>none</code> or <code>hidden</code></li><li><a href="border-right-width"><code>border-right-width</code></a>: the absolute length or <code>0</code> if <a href="border-right-style"><code>border-right-style</code></a> is <code>none</code> or <code>hidden</code></li><li><a href="border-top-width"><code>border-top-width</code></a>: the absolute length or <code>0</code> if <a href="border-top-style"><code>border-top-style</code></a> is <code>none</code> or <code>hidden</code></li></ul></li><li><a href="border-style"><code>border-style</code></a>: as each of the properties of the shorthand:<br />
<ul><li><a href="border-bottom-style"><code>border-bottom-style</code></a>: as specified</li><li><a href="border-left-style"><code>border-left-style</code></a>: as specified</li><li><a href="border-right-style"><code>border-right-style</code></a>: as specified</li><li><a href="border-top-style"><code>border-top-style</code></a>: as specified</li></ul></li><li><a href="border-inline-start-color"><code>border-inline-start-color</code></a>: computed color</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-inline-start-color"><code>border-inline-start-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="border-inline-start-style"><code>border-inline-start-style</code></a>: discrete</li><li><a href="border-inline-start-width"><code>border-inline-start-width</code></a>: a <a href="length#interpolation">length</a></li></ul></td></tr></tbody></table>

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

### HTML

    <div>
      <p class="exampleText">Example text</p>
    </div>

### CSS

    div {
      background-color: yellow;
      width: 120px;
      height: 120px;
    }

    .exampleText {
      writing-mode: vertical-rl;
      border-inline-start: 5px dashed blue;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-border-inline-start">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'border-inline-start' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-inline-start`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start</a>
