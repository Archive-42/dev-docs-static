# ::first-line (:first-line)

The `::first-line` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-element](pseudo-elements) applies styles to the first line of a [block-level element](visual_formatting_model#block-level_elements_and_block_boxes). Note that the length of the first line depends on many factors, including the width of the element, the width of the document, and the font size of the text.

    /* Selects the first line of a <p> */
    p::first-line {
      color: red;
    }

CSS3 introduced the `::first-line` notation (with two colons) to distinguish [pseudo-classes](pseudo-classes) from [pseudo-elements](pseudo-elements). Browsers also accept `:first-line`, introduced in CSS2.

## Allowable properties

Only a small subset of CSS properties can be used with the `::first-line` pseudo-element:

- All font-related properties: [`font`](font), [`font-kerning`](font-kerning), [`font-style`](font-style), [`font-variant`](font-variant), [`font-variant-numeric`](font-variant-numeric), [`font-variant-position`](font-variant-position), [`font-variant-east-asian`](font-variant-east-asian), [`font-variant-caps`](font-variant-caps), [`font-variant-alternates`](font-variant-alternates), [`font-variant-ligatures`](font-variant-ligatures), [`font-synthesis`](font-synthesis), [`font-feature-settings`](font-feature-settings), [`font-language-override`](font-language-override), [`font-weight`](font-weight), [`font-size`](font-size), [`font-size-adjust`](font-size-adjust), [`font-stretch`](font-stretch), and [`font-family`](font-family)
- All background-related properties: [`background-color`](background-color), [`background-clip`](background-clip), [`background-image`](background-image), [`background-origin`](background-origin), [`background-position`](background-position), [`background-repeat`](background-repeat), [`background-size`](background-size), [`background-attachment`](background-attachment), and [`background-blend-mode`](background-blend-mode)
- The [`color`](color) property
- [`word-spacing`](word-spacing), [`letter-spacing`](letter-spacing), [`text-decoration`](text-decoration), [`text-transform`](text-transform), and [`line-height`](line-height)
- [`text-shadow`](text-shadow), [`text-decoration`](text-decoration), [`text-decoration-color`](text-decoration-color), [`text-decoration-line`](text-decoration-line), [`text-decoration-style`](text-decoration-style), and [`vertical-align`](vertical-align).

## Syntax

    /* CSS3 syntax */
    ::first-line

    /* CSS2 syntax */
    :first-line

## Examples

### HTML

    <p>Styles will only be applied to the first line of this paragraph.
    After that, all text will be styled like normal. See what I mean?</p>

    <span>The first line of this text will not receive special styling
    because it is not a block-level element.</span>

### CSS

    ::first-line {
      color: blue;
      text-transform: uppercase;

      /* WARNING: DO NOT USE THESE */
      /* Many properties are invalid in ::first-line pseudo-elements */
      margin-left: 20px;
      text-indent: 20px;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-pseudo-4/#first-line-pseudo">CSS Pseudo-Elements Level 4<br />
<span class="small">The definition of '::first-line' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines more strictly where <code>::first-letter</code> can occur.<br />
Generalizes allowed properties to typesetting, text decoration, and inline layout properties and <a href="opacity"><code>opacity</code></a>.<br />
Defines the inheritance of <code>::first-letter</code>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-text-decor-3/#text-shadow-property">CSS Text Decoration Module Level 3<br />
<span class="small">The definition of 'text-shadow with ::first-line' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Allows the use of <a href="text-shadow"><code>text-shadow</code></a> with <code>::first-letter</code>.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-3/#first-line">Selectors Level 3<br />
<span class="small">The definition of '::first-line' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Introduction of the two-colon syntax.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/selector.html#first-line-pseudo">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '::first-line' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#the-first-line-pseudo-element">CSS Level 1<br />
<span class="small">The definition of '::first-line' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition, using the one-colon syntax.</td></tr></tbody></table>

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

`::first-line`

1

Before Chrome 62, the [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work on `::first-line` pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

1

Before Chrome 62, the [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work on `::first-line` pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

12

12

1

1

9

5.5

7

From Opera 15 to Opera 49 (exclusive), the [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work on `::first-line` or `:first-line` pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

3.5

From Opera 15 to Opera 49 (exclusive), the [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work on `::first-line` or `:first-line` pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

1

The [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work for `::first-line` or `:first-line` pseudo-elements. See [WebKit bug 3409](https://webkit.org/b/3409).

1

The [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work for `::first-line` or `:first-line` pseudo-elements. See [WebKit bug 3409](https://webkit.org/b/3409).

≤37

Before WebView 62, the [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work on `::first-line` pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

≤37

Before WebView 62, the [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work on `::first-line` pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

18

Before Chrome 62, the [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work on `::first-line` pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

18

Before Chrome 62, the [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work on `::first-line` pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

4

4

10.1

From Opera 15 to Opera 49 (exclusive), the [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work on `::first-line` or `:first-line` pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

10.1

From Opera 15 to Opera 49 (exclusive), the [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work on `::first-line` or `:first-line` pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

1

The [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work for `::first-line` or `:first-line` pseudo-elements. See [WebKit bug 3409](https://webkit.org/b/3409).

1

The [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work for `::first-line` or `:first-line` pseudo-elements. See [WebKit bug 3409](https://webkit.org/b/3409).

1.0

Before Samsung Internet 8.0, the [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work on `::first-line` pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

1.0

Before Samsung Internet 8.0, the [`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform) property does not work on `::first-line` pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

## See also

- [`::first-letter`](::first-letter)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line</a>
