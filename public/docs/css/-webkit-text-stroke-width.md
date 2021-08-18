# -webkit-text-stroke-width

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `-webkit-text-stroke-width` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the width of the stroke for text.

## Syntax

    /* Keyword values */
    -webkit-text-stroke-width: thin;
    -webkit-text-stroke-width: medium;
    -webkit-text-stroke-width: thick;

    /* <length> values */
    -webkit-text-stroke-width: 2px;
    -webkit-text-stroke-width: 0.1em;
    -webkit-text-stroke-width: 1mm;
    -webkit-text-stroke-width: 5pt;

    /* Global values */
    -webkit-text-stroke-width: inherit;
    -webkit-text-stroke-width: initial;
    -webkit-text-stroke-width: unset;

### Values

`<line-width>`  
The width of the stroke.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>absolute <a href="length"><code>&lt;length&gt;</code></a></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <length>

## Examples

### Varying stroke widths

#### CSS

    p {
      margin: 0;
      font-size: 4em;
      -webkit-text-stroke-color: red;
    }

    #thin {
      -webkit-text-stroke-width: thin;
    }

    #medium {
      -webkit-text-stroke-width: 3px;
    }

    #thick {
      -webkit-text-stroke-width: 1.5mm;
    }

#### HTML

    <p id="thin">Thin stroke</p>
    <p id="medium">Medium stroke</p>
    <p id="thick">Thick stroke</p>

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://compat.spec.whatwg.org/#the-webkit-text-stroke-width">Compatibility Standard<br />
<span class="small">The definition of '-webkit-text-stroke-width' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial standardization</td></tr><tr class="even"><td><a href="https://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariCSSRef/Articles/StandardCSSProperties.html#//apple_ref/doc/uid/TP30001266--webkit-text-stroke-width">Safari CSS Reference<br />
<span class="small">'-webkit-text-stroke-width' in that document.</span></a></td><td>Non-standard unofficial documentation</td><td>Initial documentation</td></tr></tbody></table>

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

`-webkit-text-stroke-width`

1

15

49

48

No

15

3

38

18

49

48

15

2

1.0

## See also

- [Surfin' Safari blog post announcing this feature](https://www.webkit.org/blog/85/introducing-text-stroke/)
- [CSS-Tricks article explaining this feature](https://css-tricks.com/adding-stroke-to-web-text/)
- [`-webkit-text-stroke-color`](-webkit-text-stroke-color)
- [`-webkit-text-stroke`](-webkit-text-stroke)
- [`-webkit-text-fill-color`](-webkit-text-fill-color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke-width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke-width</a>
