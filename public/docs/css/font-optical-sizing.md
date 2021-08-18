# font-optical-sizing

The `font-optical-sizing` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether text rendering is optimized for viewing at different sizes.

## Syntax

    /* keyword values */
    font-optical-sizing: none;
    font-optical-sizing: auto; /* default */

    /* Global values */
    font-optical-sizing: inherit;
    font-optical-sizing: initial;
    font-optical-sizing: unset;

### Values

none  
The browser will not modify the shape of glyphs for optimal viewing.

auto  
The browser will modify the shape of glyphs for optimal viewing.

## Description

Optical sizing is enabled by default for fonts that have an optical size variation axis. The optical size variation axis is represented by `opsz` in [`font-variation-settings`](font-variation-settings).

When optical sizing is used, small text sizes are often rendered with thicker strokes and larger serifs, whereas larger text is often rendered more delicately with more contrast between thicker and thinner strokes.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | none

## Examples

### Disabling optical sizing

    <p class="optical-sizing">This paragraph is optically sized.
     This is the default across browsers.</p>

    <p class="no-optical-sizing">This paragraph is not optically sized.
     You should see a difference in supporting browsers.</p>

    @font-face {
        src: url('AmstelvarAlpha-VF.ttf');
        font-family:'Amstelvar';
        font-style: normal;
    }

    p {
      font-size: 36px;
      font-family: Amstelvar;
    }

    .no-optical-sizing {
      font-optical-sizing: none;
    }

**Note**: The font referenced above — which includes optical sizing and is freely-licensed — is good for testing. You can [download it on GitHub](https://github.com/TypeNetwork/Amstelvar/releases).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#font-optical-sizing-def">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'font-optical-sizing' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`font-optical-sizing`

79

17

62

No

66

11

79

79

62

No

11

12.0

## See also

- [`font-size`](font-size)
- [`font-size-adjust`](font-size-adjust)
- [Fundamental text and font styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-optical-sizing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-optical-sizing</a>
