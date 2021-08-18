# border

The `border` [shorthand](shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets an element's border. It sets the values of [`border-width`](border-width), [`border-style`](border-style), and [`border-color`](border-color).

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`border-color`](border-color)
- [`border-style`](border-style)
- [`border-width`](border-width)

## Syntax

    /* style */
    border: solid;

    /* width | style */
    border: 2px dotted;

    /* style | color */
    border: outset #f33;

    /* width | style | color */
    border: medium dashed green;

    /* Global values */
    border: inherit;
    border: initial;
    border: unset;

The `border` property may be specified using one, two, or three of the values listed below. The order of the values does not matter.

**Note:** The border will be invisible if its style is not defined. This is because the style defaults to `none`.

### Values

`<line-width>`  
Sets the thickness of the border. Defaults to `medium` if absent. See [`border-width`](border-width).

`<line-style>`  
Sets the style of the border. Defaults to `none` if absent. See [`border-style`](border-style).

[`<color>`](color_value)  
Sets the color of the border. Defaults to `currentcolor` if absent. See [`border-color`](border-color).

## Description

As with all shorthand properties, any omitted sub-values will be set to their [initial value](initial_value). Importantly, `border` cannot be used to specify a custom value for [`border-image`](border-image), but instead sets it to its initial value, i.e., `none`.

The `border` shorthand is especially useful when you want all four borders to be the same. To make them different from each other, however, you can use the longhand [`border-width`](border-width), [`border-style`](border-style), and [`border-color`](border-color) properties, which accept different values for each side. Alternatively, you can target one border at a time with the physical (e.g., [`border-top`](border-top) ) and logical (e.g., [`border-block-start`](border-block-start)) border properties.

### Borders vs. outlines

Borders and [outlines](outline) are very similar. However, outlines differ from borders in the following ways:

- Outlines never take up space, as they are drawn outside of an element's content.
- According to the spec, outlines don't have to be rectangular, although they usually are.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-width"><code>border-width</code></a>: as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-width"><code>border-top-width</code></a>: <code>medium</code></li><li><a href="border-right-width"><code>border-right-width</code></a>: <code>medium</code></li><li><a href="border-bottom-width"><code>border-bottom-width</code></a>: <code>medium</code></li><li><a href="border-left-width"><code>border-left-width</code></a>: <code>medium</code></li></ul></li><li><a href="border-style"><code>border-style</code></a>: as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-style"><code>border-top-style</code></a>: <code>none</code></li><li><a href="border-right-style"><code>border-right-style</code></a>: <code>none</code></li><li><a href="border-bottom-style"><code>border-bottom-style</code></a>: <code>none</code></li><li><a href="border-left-style"><code>border-left-style</code></a>: <code>none</code></li></ul></li><li><a href="border-color"><code>border-color</code></a>: as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-color"><code>border-top-color</code></a>: <code>currentcolor</code></li><li><a href="border-right-color"><code>border-right-color</code></a>: <code>currentcolor</code></li><li><a href="border-bottom-color"><code>border-bottom-color</code></a>: <code>currentcolor</code></li><li><a href="border-left-color"><code>border-left-color</code></a>: <code>currentcolor</code></li></ul></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-width"><code>border-width</code></a>: as each of the properties of the shorthand:<br />
<ul><li><a href="border-bottom-width"><code>border-bottom-width</code></a>: the absolute length or <code>0</code> if <a href="border-bottom-style"><code>border-bottom-style</code></a> is <code>none</code> or <code>hidden</code></li><li><a href="border-left-width"><code>border-left-width</code></a>: the absolute length or <code>0</code> if <a href="border-left-style"><code>border-left-style</code></a> is <code>none</code> or <code>hidden</code></li><li><a href="border-right-width"><code>border-right-width</code></a>: the absolute length or <code>0</code> if <a href="border-right-style"><code>border-right-style</code></a> is <code>none</code> or <code>hidden</code></li><li><a href="border-top-width"><code>border-top-width</code></a>: the absolute length or <code>0</code> if <a href="border-top-style"><code>border-top-style</code></a> is <code>none</code> or <code>hidden</code></li></ul></li><li><a href="border-style"><code>border-style</code></a>: as each of the properties of the shorthand:<br />
<ul><li><a href="border-bottom-style"><code>border-bottom-style</code></a>: as specified</li><li><a href="border-left-style"><code>border-left-style</code></a>: as specified</li><li><a href="border-right-style"><code>border-right-style</code></a>: as specified</li><li><a href="border-top-style"><code>border-top-style</code></a>: as specified</li></ul></li><li><a href="border-color"><code>border-color</code></a>: as each of the properties of the shorthand:<br />
<ul><li><a href="border-bottom-color"><code>border-bottom-color</code></a>: computed color</li><li><a href="border-left-color"><code>border-left-color</code></a>: computed color</li><li><a href="border-right-color"><code>border-right-color</code></a>: computed color</li><li><a href="border-top-color"><code>border-top-color</code></a>: computed color</li></ul></li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-color"><code>border-color</code></a>: as each of the properties of the shorthand:<br />
<ul><li><a href="border-bottom-color"><code>border-bottom-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="border-left-color"><code>border-left-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="border-right-color"><code>border-right-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="border-top-color"><code>border-top-color</code></a>: a <a href="color_value#interpolation">color</a></li></ul></li><li><a href="border-style"><code>border-style</code></a>: discrete</li><li><a href="border-width"><code>border-width</code></a>: as each of the properties of the shorthand:<br />
<ul><li><a href="border-bottom-width"><code>border-bottom-width</code></a>: a <a href="length#interpolation">length</a></li><li><a href="border-left-width"><code>border-left-width</code></a>: a <a href="length#interpolation">length</a></li><li><a href="border-right-width"><code>border-right-width</code></a>: a <a href="length#interpolation">length</a></li><li><a href="border-top-width"><code>border-top-width</code></a>: a <a href="length#interpolation">length</a></li></ul></li></ul></td></tr></tbody></table>

## Formal syntax

    <line-width> || <line-style> || <color>where
    <line-width> = <length> | thin | medium | thick
    <line-style> = none | hidden | dotted | dashed | solid | double | groove | ridge | inset | outset
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

## Examples

### Setting a pink outset border

#### HTML

    <div>I have a border, an outline, and a box shadow! Amazing, isn't it?</div>

#### CSS

    div {
      border: 0.5rem outset pink;
      outline: 0.5rem solid khaki;
      box-shadow: 0 0 0 2rem skyblue;
      border-radius: 12px;
      font: bold 1rem sans-serif;
      margin: 2rem;
      padding: 1rem;
      outline-offset: 0.5rem;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-border-shorthands">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Removes <em>specific</em> support for <code>transparent</code>, as it is now a valid <a href="color_value"><code>&lt;color&gt;</code></a>; this has no practical impact.<br />
Though it cannot be set to a custom value using the shorthand, <code>border</code> now resets <a href="border-image"><code>border-image</code></a> to its initial value (<code>none</code>).</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#border-shorthand-properties">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'border' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Accepts the <code>inherit</code> keyword. Also accepts <code>transparent</code> as a valid color.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#border">CSS Level 1<br />
<span class="small">The definition of 'border' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`border`

1

12

1

4

3.5

1

≤37

18

4

14

1

1.0

## See also

- [`border-width`](border-width)
- [`border-style`](border-style)
- [`border-color`](border-color)
- [Backgrounds and borders](css_backgrounds_and_borders)
- [Learn CSS: Backgrounds and borders](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Backgrounds_and_borders)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border</a>
