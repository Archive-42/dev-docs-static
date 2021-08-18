# opacity

The `opacity` CSS property sets the opacity of an element. Opacity is the degree to which content behind an element is hidden, and is the opposite of transparency.

## Syntax

### Values

`<alpha-value>`  
A [`<number>`](number) in the range `0.0` to `1.0`, inclusive, or a [`<percentage>`](percentage) in the range `0%` to `100%`, inclusive, representing the opacity of the channel (that is, the value of its alpha channel). Any value outside the interval, though valid, is clamped to the nearest limit in the range.

<table><thead><tr class="header"><th>Value</th><th>Meaning</th></tr></thead><tbody><tr class="odd"><td><code>0</code></td><td>The element is fully transparent (that is, invisible).</td></tr><tr class="even"><td>Any <a href="number"><code>&lt;number&gt;</code></a> strictly between <code>0</code> and <code>1</code></td><td>The element is translucent (that is, content behind the element can be seen).</td></tr><tr class="odd"><td><code>1</code> (default value)</td><td>The element is fully opaque (visually solid).</td></tr></tbody></table>

## Description

`opacity` applies to the element as a whole, including its contents, even though the value is not inherited by child elements. Thus, the element and its children all have the same opacity relative to the element's background, even if they have different opacities relative to one another.

Using `opacity` with a value other than `1` places the element in a new [stacking context](css_positioning/understanding_z_index/the_stacking_context).

If you [do not want to apply opacity to child elements](https://stackoverflow.com/questions/13508877/resetting-the-opacity-of-a-child-elements-maple-browser-samsung-tv-app), use the [`background`](background) property instead. For example:

    background: rgba(0, 0, 0, 0.4);

## Accessibility concerns

If text opacity is adjusted, it is important to ensure that the contrast ratio between the color of the text and the background the text is placed over is high enough that people experiencing low vision conditions will be able to read the content of the page.

Color contrast ratio is determined by comparing the luminosity of the opacity-adjusted text and background color values. In order to meet current [Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/intro/wcag), a ratio of 4.5:1 is required for text content and 3:1 for larger text such as headings. Large text is defined as 18.66px and [bold](font-weight) or larger, or 24px or larger.

- [WebAIM: Color Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.3 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>1.0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>the specified value, clipped in the range <code>[0,1]</code></td></tr><tr class="odd"><td>Animation type</td><td>a <a href="number#interpolation">number</a></td></tr></tbody></table>

## Formal syntax

    <alpha-value>where
    <alpha-value> = <number> | <percentage>

## Examples

### Setting background opacity

#### HTML

    <div class="light">You can barely see this.</div>
    <div class="medium">This is easier to see.</div>
    <div class="heavy">This is very easy to see.</div>

#### CSS

    div { background-color: yellow; }
    .light {
      opacity: 0.2; /* Barely see the text over the background */
    }
    .medium {
      opacity: 0.5; /* See the text more clearly over the background */
    }
    .heavy {
      opacity: 0.9; /* See the text very clearly over the background */
    }

#### Result

### Setting opacity on hover

#### HTML

    <img src="//developer.mozilla.org/static/img/opengraph-logo.png"
      alt="MDN logo" width="128" height="146"
      class="opacity">

#### CSS

    img.opacity {
      opacity: 1;
      filter: alpha(opacity=100); /* IE8 and lower */
      zoom: 1; /* Triggers "hasLayout" in IE 7 and lower */
    }

    img.opacity:hover {
      opacity: 0.5;
      filter: alpha(opacity=50);
      zoom: 1;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-color/#transparency">CSS Color Module Level 4<br />
<span class="small">The definition of 'opacity' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines percentage opacity values.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-color-3/#opacity">CSS Color Module Level 3<br />
<span class="small">The definition of 'opacity' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`opacity`

1

12

1

1-3.5

9

9

2

1.1-2

1

18

4

10.1

1

1.0

`percentages`

78

79

70

No

No

No

78

78

No

No

No

12.0

## See also

- [Microsoft's filter:alpha(opacity=xx)](https://msdn.microsoft.com/en-us/library/ms532910%28VS.85%29.aspx)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/opacity" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/opacity</a>
