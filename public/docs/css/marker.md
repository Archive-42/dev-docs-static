# ::marker

The `::marker` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-element](pseudo-elements) selects the marker box of a list item, which typically contains a bullet or number. It works on any element or pseudo-element set to `display: list-item`, such as the [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) and [`<summary>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary) elements.

    ::marker {
      color: blue;
      font-size: 1.2em;
    }

## Allowable properties

Only certain CSS properties can be used in a rule with `::marker` as a selector:

- All [font properties](css_fonts)
- The [`white-space`](white-space) property
- [`color`](color)
- [`text-combine-upright`](text-combine-upright), [`unicode-bidi`](unicode-bidi) and [`direction`](direction) properties
- The [`content`](content) property
- All [animation](css_animations#css_properties) and [transition](css_transitions#properties) properties

The specification states that additional CSS properties may be supported in future.

## Syntax

    ::marker

## Examples

### HTML

    <ul>
      <li>Peaches</li>
      <li>Apples</li>
      <li>Plums</li>
    </ul>

### CSS

    ul li::marker {
      color: red;
      font-size: 1.5em;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-pseudo-4/#marker-pseudo">CSS Pseudo-Elements Level 4<br />
<span class="small">The definition of '::marker' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No significant change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-lists-3/#marker-pseudo">CSS Lists Module Level 3<br />
<span class="small">The definition of '::marker' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`::marker`

86

80

86

80

68

No

72

11.1

Safari support is limited to `color` and `font-size`. See [bug 204163](https://webkit.org/b/204163)

86

86

80

68

61

11.3

Safari support is limited to `color` and `font-size`. See [bug 204163](https://webkit.org/b/204163)

No

`animation_and_transition_support`

86

83

86

83

80

No

72

No

86

86

83

No

61

No

No

## See also

- HTML elements that have marker boxes by default: [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol), [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li), [`<summary>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/::marker" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/::marker</a>
