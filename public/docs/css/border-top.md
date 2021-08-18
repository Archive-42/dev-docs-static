# border-top

The `border-top` [shorthand](shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets all the properties of an element's top [border](border).

As with all shorthand properties, `border-top` always sets the values of all of the properties that it can set, even if they are not specified. It sets those that are not specified to their default values. This means that ...

    border-top-style: dotted;
    border-top: thick green;

... is actually the same as ...

    border-top-style: dotted;
    border-top: none thick green;

... and the value of [`border-top-style`](border-top-style) given before `border-top` is ignored. Since the default value of [`border-top-style`](border-top-style) is `none`, not specifying the `border-style` part results in no border.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`border-top-color`](border-top-color)
- [`border-top-style`](border-top-style)
- [`border-top-width`](border-top-width)

## Syntax

    border-top: 1px;
    border-top: 2px dotted;
    border-top: medium dashed green;

The three values of the shorthand property can be specified in any order, and one or two of them may be omitted.

### Values

`<br-width>`  
See [`border-top-width`](border-top-width).

`<br-style>`  
See [`border-top-style`](border-top-style).

[`<color>`](color_value)  
See [`border-top-color`](border-top-color).

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-width"><code>border-top-width</code></a>: <code>medium</code></li><li><a href="border-top-style"><code>border-top-style</code></a>: <code>none</code></li><li><a href="border-top-color"><code>border-top-color</code></a>: <code>currentcolor</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-width"><code>border-top-width</code></a>: the absolute length or <code>0</code> if <a href="border-top-style"><code>border-top-style</code></a> is <code>none</code> or <code>hidden</code></li><li><a href="border-top-style"><code>border-top-style</code></a>: as specified</li><li><a href="border-top-color"><code>border-top-color</code></a>: computed color</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-color"><code>border-top-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="border-top-style"><code>border-top-style</code></a>: discrete</li><li><a href="border-top-width"><code>border-top-width</code></a>: a <a href="length#interpolation">length</a></li></ul></td></tr></tbody></table>

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

### Applying a top border

#### HTML

    <div>
      This box has a border on the top side.
    </div>

#### CSS

    div {
      border-top: 4px dashed blue;
      background-color: gold;
      height: 100px;
      width: 100px;
      font-weight: bold;
      text-align: center;
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#propdef-border-top">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-top' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No direct changes, though the modification of values for the <a href="border-top-color"><code>border-top-color</code></a> do apply to it.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#propdef-border-top">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'border-top' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant changes.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#border-top">CSS Level 1<br />
<span class="small">The definition of 'border-top' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-top`

1

12

1

4

3.5

1

1

18

4

14

1

1.0

## See also

- `border`
- `border-block`
- `outline`

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-top" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-top</a>
