# background-clip

The `background-clip` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether an element's background extends underneath its border box, padding box, or content box.

If the element has no [`background-image`](background-image) or [`background-color`](background-color), this property will only have a visual effect when the border has transparent regions or partially opaque regions (due to [`border-style`](border-style) or [`border-image`](border-image)); otherwise, the border masks the difference.

**Note:** Because the [root element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) has a different background painting area, the `background-clip` property has no effect when specified on it. See "[The backgrounds of special elements.](https://drafts.csswg.org/css-backgrounds-3/#special-backgrounds)"

**Note:** For documents whose [root element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) is an HTML element: if the computed value of [`background-image`](background-image) on the root element is `none` and its [`background-color`](background-color) is `transparent`, user agents must instead propagate the computed values of the `background` properties from that element’s first HTML [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) child element. The used values of that `<body>` element’s `background` properties are their initial values, and the propagated values are treated as if they were specified on the root element. It is recommended that authors of HTML documents specify the canvas background for the `<body>` element rather than the HTML element.

## Syntax

    /* Keyword values */
    background-clip: border-box;
    background-clip: padding-box;
    background-clip: content-box;
    background-clip: text;

    /* Global values */
    background-clip: inherit;
    background-clip: initial;
    background-clip: unset;

### Values

`border-box`  
The background extends to the outside edge of the border (but underneath the border in z-ordering).

`padding-box`  
The background extends to the outside edge of the padding. No background is drawn beneath the border.

`content-box`  
The background is painted within (clipped to) the content box.

`text` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The background is painted within (clipped to) the foreground text.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>border-box</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <box>#where
    <box> = border-box | padding-box | content-box

## Examples

### HTML

    <p class="border-box">The background extends behind the border.</p>
    <p class="padding-box">The background extends to the inside edge of the border.</p>
    <p class="content-box">The background extends only to the edge of the content box.</p>
    <p class="text">The background is clipped to the foreground text.</p>

### CSS

    p {
      border: .8em darkviolet;
      border-style: dotted double;
      margin: 1em 0;
      padding: 1.4em;
      background: linear-gradient(60deg, red, yellow, red, yellow, red);
      font: 900 1.2em sans-serif;
      text-decoration: underline;
    }

    .border-box { background-clip: border-box; }
    .padding-box { background-clip: padding-box; }
    .content-box { background-clip: content-box; }

    .text {
      background-clip: text;
      -webkit-background-clip: text;
      color: rgba(0,0,0,.2);
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-background-clip">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'background-clip' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-backgrounds-4/#background-clip">CSS Backgrounds and Borders Module Level 4<br />
<span class="small">The definition of 'background-clip' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Add <code>text</code> value.</td></tr></tbody></table>

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

`background-clip`

1

1-64

Chrome accepts alternate synonyms to its values: `padding`, `border`, and `content`.

12

4

49

1-4

Used the `-moz-background-clip: padding | border` syntax.

9

In IE 7 and IE 8 of Internet Explorer, this property always behaved like `background-clip: padding` when `overflow` was `hidden`, `auto`, or `scroll`.

10.5

15-51

Opera accepts alternate synonyms to its values: `padding`, `border`, and `content`.

3

Safari accepts alternate synonyms to its values: `padding`, `border`, and `content`.

4.1

≤37-64

WebView accepts alternate synonyms to its values: `padding`, `border`, and `content`.

18

18-64

Chrome accepts alternate synonyms to its values: `padding`, `border`, and `content`.

14

49

11

14-47

Opera accepts alternate synonyms to its values: `padding`, `border`, and `content`.

1

Safari accepts alternate synonyms to its values: `padding`, `border`, and `content`.

1.0

1.0-9.0

Chrome accepts alternate synonyms to its values: `padding`, `border`, and `content`.

`content-box`

1

12

4

9

In IE 7 and IE 9 of Internet Explorer, it always behaved like `background-clip: padding` if `overflow: hidden | auto | scroll`

10.5

3

4.1

18

14

11

1

1.0

`text`

3

\["This value is supported with the prefixed version of the property only.", "According to the [WebKit blog](https://webkit.org/blog/164/background-clip-text/), text decorations or shadows are not included in the clipping."\]

15

12

Before Edge 15, this value was supported with the prefixed version of the property only.

49

No

15

\["This value is supported with the prefixed version of the property only.", "According to the [WebKit blog](https://webkit.org/blog/164/background-clip-text/), text decorations or shadows are not included in the clipping."\]

4

\["This value is supported with the prefixed version of the property only.", "According to the [WebKit blog](https://webkit.org/blog/164/background-clip-text/), text decorations or shadows are not included in the clipping."\]

≤37

\["This value is supported with the prefixed version of the property only.", "According to the [WebKit blog](https://webkit.org/blog/164/background-clip-text/), text decorations or shadows are not included in the clipping."\]

18

\["This value is supported with the prefixed version of the property only.", "According to the [WebKit blog](https://webkit.org/blog/164/background-clip-text/), text decorations or shadows are not included in the clipping."\]

49

14

\["This value is supported with the prefixed version of the property only.", "According to the [WebKit blog](https://webkit.org/blog/164/background-clip-text/), text decorations or shadows are not included in the clipping."\]

3.2

\["This value is supported with the prefixed version of the property only.", "According to the [WebKit blog](https://webkit.org/blog/164/background-clip-text/), text decorations or shadows are not included in the clipping."\]

1.0

\["This value is supported with the prefixed version of the property only.", "According to the [WebKit blog](https://webkit.org/blog/164/background-clip-text/), text decorations or shadows are not included in the clipping."\]

## See also

- The [`clip-path`](clip-path) property creates a clipping region that defines what part of an _entire element_ should be displayed.
- Background properties: [`background`](background), [`background-color`](background-color), [`background-image`](background-image), [`background-origin`](background-origin)
- [Introduction to the CSS box model](css_box_model/introduction_to_the_css_box_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-clip" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/background-clip</a>
