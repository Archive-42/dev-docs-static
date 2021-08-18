# border-right

The `border-right` [shorthand](shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets all the properties of an element's right [border](border).

As with all shorthand properties, `border-right` always sets the values of all of the properties that it can set, even if they are not specified. It sets those that are not specified to their default values. This means that ...

    border-right-style: dotted;
    border-right: thick green;

... is actually the same as ...

    border-right-style: dotted;
    border-right: none thick green;

... and the value of [`border-right-style`](border-right-style) given before `border-right` is ignored. Since the default value of [`border-right-style`](border-right-style) is `none`, not specifying the `border-style` part results in no border.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`border-right-color`](border-right-color)
- [`border-right-style`](border-right-style)
- [`border-right-width`](border-right-width)

## Syntax

    border-right: 1px;
    border-right: 2px dotted;
    border-right: medium dashed green;

The three values of the shorthand property can be specified in any order, and one or two of them may be omitted.

### Values

`<br-width>`  
See [`border-right-width`](border-right-width).

`<br-style>`  
See [`border-right-style`](border-right-style).

[`<color>`](color_value)  
See [`border-right-color`](border-right-color).

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-right-width"><code>border-right-width</code></a>: <code>medium</code></li><li><a href="border-right-style"><code>border-right-style</code></a>: <code>none</code></li><li><a href="border-right-color"><code>border-right-color</code></a>: <code>currentcolor</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-right-width"><code>border-right-width</code></a>: the absolute length or <code>0</code> if <a href="border-right-style"><code>border-right-style</code></a> is <code>none</code> or <code>hidden</code></li><li><a href="border-right-style"><code>border-right-style</code></a>: as specified</li><li><a href="border-right-color"><code>border-right-color</code></a>: computed color</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-right-color"><code>border-right-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="border-right-style"><code>border-right-style</code></a>: discrete</li><li><a href="border-right-width"><code>border-right-width</code></a>: a <a href="length#interpolation">length</a></li></ul></td></tr></tbody></table>

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

### Applying a right border

#### HTML

    <div>
      This box has a border on the right side.
    </div>

#### CSS

    div {
      border-right: 4px dashed blue;
      background-color: gold;
      height: 100px;
      width: 100px;
      font-weight: bold;
      text-align: center;
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#propdef-border-right">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-right' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No direct changes, though the modification of values for the <a href="border-right-color"><code>border-right-color</code></a> do apply to it.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#propdef-border-right">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'border-right' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant changes.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#border-right">CSS Level 1<br />
<span class="small">The definition of 'border-right' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-right`

1

12

1

5.5

9.2

1

≤37

18

14

14

1

1.0

## See also

- [`border`](border)
- [`border-block`](border-block)
- [`outline`](outline)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-right" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-right</a>
