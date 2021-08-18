# text-decoration

The `text-decoration` [shorthand](shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the appearance of decorative lines on text. It is a shorthand for [`text-decoration-line`](text-decoration-line), [`text-decoration-color`](text-decoration-color), [`text-decoration-style`](text-decoration-style), and the newer [`text-decoration-thickness`](text-decoration-thickness) property.

Text decorations are drawn across descendant text elements. This means that if an element specifies a text decoration, then a child element can't remove the decoration. For example, in the markup `<p>This text has <em>some emphasized words</em> in it.</p>`, the style rule `p { text-decoration: underline; }` would cause the entire paragraph to be underlined. The style rule `em { text-decoration: none; }` would not cause any change; the entire paragraph would still be underlined. However, the rule `em { text-decoration: overline; }` would cause a second decoration to appear on "some emphasized words".

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`text-decoration-color`](text-decoration-color)
- [`text-decoration-line`](text-decoration-line)
- [`text-decoration-style`](text-decoration-style)
- [`text-decoration-thickness`](text-decoration-thickness)

## Syntax

The `text-decoration` property is specified as one or more space-separated values representing the various longhand text-decoration properties.

### Values

[`text-decoration-line`](text-decoration-line)  
Sets the kind of decoration used, such as `underline` or `line-through`.

[`text-decoration-color`](text-decoration-color)  
Sets the color of the decoration.

[`text-decoration-style`](text-decoration-style)  
Sets the style of the line used for the decoration, such as `solid`, `wavy`, or `dashed`.

[`text-decoration-thickness`](text-decoration-thickness)  
Sets the thickness of the line used for the decoration.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="text-decoration-color"><code>text-decoration-color</code></a>: <code>currentcolor</code></li><li><a href="text-decoration-style"><code>text-decoration-style</code></a>: <code>solid</code></li><li><a href="text-decoration-line"><code>text-decoration-line</code></a>: <code>none</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="text-decoration-line"><code>text-decoration-line</code></a>: as specified</li><li><a href="text-decoration-style"><code>text-decoration-style</code></a>: as specified</li><li><a href="text-decoration-color"><code>text-decoration-color</code></a>: computed color</li><li><a href="text-decoration-thickness"><code>text-decoration-thickness</code></a>: as specified</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="text-decoration-color"><code>text-decoration-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="text-decoration-style"><code>text-decoration-style</code></a>: discrete</li><li><a href="text-decoration-line"><code>text-decoration-line</code></a>: discrete</li><li><a href="text-decoration-thickness"><code>text-decoration-thickness</code></a>: by computed value type</li></ul></td></tr></tbody></table>

## Formal syntax

    <'text-decoration-line'> || <'text-decoration-style'> || <'text-decoration-color'> || <'text-decoration-thickness'>

## Examples

### Demonstration of text-decoration values

    .under {
      text-decoration: underline red;
    }

    .over {
      text-decoration: wavy overline lime;
    }

    .line {
      text-decoration: line-through;
    }

    .plain {
      text-decoration: none;
    }

    .underover {
      text-decoration: dashed underline overline;
    }

    .thick {
      text-decoration: solid underline purple 4px;
    }

    .blink {
      text-decoration: blink;
    }

    <p class="under">This text has a line underneath it.</p>
    <p class="over">This text has a line over it.</p>
    <p class="line">This text has a line going through it.</p>
    <p>This <a class="plain" href="#">link will not be underlined</a>,
        as links generally are by default. Be careful when removing
        the text decoration on anchors since users often depend on
        the underline to denote hyperlinks.</p>
    <p class="underover">This text has lines above <em>and</em> below it.</p>
    <p class="thick">This text has a really thick purple underline in supporting browsers.</p>
    <p class="blink">This text might blink for you,
        depending on the browser you use.</p>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-4/">CSS Text Decoration Module Level 4</a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <a href="text-decoration-thickness"><code>text-decoration-thickness</code></a>; note that this isn't yet officially part of the shorthand — this is as yet unspecified.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-text-decor-3/#text-decoration-property">CSS Text Decoration Module Level 3<br />
<span class="small">The definition of 'text-decoration' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Transformed into a shorthand property. Added support for the value of <a href="text-decoration-style"><code>text-decoration-style</code></a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/text.html#lining-striking-props">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'text-decoration' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant changes.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#text-decoration">CSS Level 1<br />
<span class="small">The definition of 'text-decoration' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`text-decoration`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`blink`

No

No

1-23

No

4-15

No

No

No

4-23

10.1-14

No

No

`shorthand`

57

79

36

6

No

44

8

57

57

36

6

43

8

7.0

`text-decoration-thickness`

87

87

70

No

73

No

87

87

No

No

No

No

## See also

- The individual text-decoration properties are [`text-decoration-line`](text-decoration-line), [`text-decoration-color`](text-decoration-color), and [`text-decoration-style`](text-decoration-style).
- The [`list-style`](list-style) attribute controls the appearance of items in HTML [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) and [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) lists.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration</a>
