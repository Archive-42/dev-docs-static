# -webkit-print-color-adjust

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `-webkit-print-color-adjust` property is a non-standard CSS extension that can be used to force printing of background colors and images in browsers based on the WebKit engine.

    /* Keyword values */
    -webkit-print-color-adjust: economy;
    -webkit-print-color-adjust: exact;

    /* Global values */
    -webkit-print-color-adjust: inherit;
    -webkit-print-color-adjust: initial;
    -webkit-print-color-adjust: unset;

## Syntax

The `-webkit-print-color-adjust` property is specified as one of the keyword values listed below.

### Values

`economy`  
Normal behavior. Background colors and images are only printed if the user explicitly allows it in their browser's print settings dialog.

`exact`  
Background colors and images of the element to which this rule is applied are always printed, user's print settings are overridden.

## Formal definition

<span style="color:red;">Value not found in DB!</span>

## Formal syntax

{{CSSSyntax}}

## Examples

### Forcing white-on-black printing

    article {
      -webkit-print-color-adjust: exact;
      background: #222;
      color: #eee;
    }

## Specifications

Not part of any standard, though there is a [proposal in the CSSWG wiki](https://wiki.csswg.org/ideas/print-backgrounds) to standardize it.

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

`-webkit-print-color-adjust`

17

\["Chrome does not print backgrounds of the [`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body) element. If this property is set to `exact` for the `<body>` element, it will apply only to its descendants.", "Before Chrome 26, if background images are clipped (for example, when using `background-image` sprites) and `-webkit-print-color-adjust` is set to `exact`, then backgrounds will appear distorted when printed. Solid backgrounds and background images that are not clipped (i.e., backgrounds that have narrower and shorter than the element to which they are applied) are printed correctly. See [Chromium bug 131054](https://crbug.com/131054)."\]

79

Edge does not print backgrounds of the [`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body) element. If this property is set to `exact` for the `<body>` element, it will apply only to its descendants.

No

No

15

Opera does not print backgrounds of the [`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body) element. If this property is set to `exact` for the `<body>` element, it will apply only to its descendants.

6

Safari does not print backgrounds of the [`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body) element. If this property is set to `exact` for the `<body>` element, it will apply only to its descendants.

37

WebView does not print backgrounds of the [`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body) element. If this property is set to `exact` for the `<body>` element, it will apply only to its descendants.

18

\["Chrome does not print backgrounds of the [`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body) element. If this property is set to `exact` for the `<body>` element, it will apply only to its descendants.", "Before Chrome 26, if background images are clipped (for example, when using `background-image` sprites) and `-webkit-print-color-adjust` is set to `exact`, then backgrounds will appear distorted when printed. Solid backgrounds and background images that are not clipped (i.e., backgrounds that have narrower and shorter than the element to which they are applied) are printed correctly. See [Chromium bug 131054](https://crbug.com/131054)."\]

No

15

Opera does not print backgrounds of the [`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body) element. If this property is set to `exact` for the `<body>` element, it will apply only to its descendants.

6

Safari does not print backgrounds of the [`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body) element. If this property is set to `exact` for the `<body>` element, it will apply only to its descendants.

1.0

\["Samsung Internet does not print backgrounds of the [`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body) element. If this property is set to `exact` for the `<body>` element, it will apply only to its descendants.", "Before Chrome 26, if background images are clipped (for example, when using `background-image` sprites) and `-webkit-print-color-adjust` is set to `exact`, then backgrounds will appear distorted when printed. Solid backgrounds and background images that are not clipped (i.e., backgrounds that have narrower and shorter than the element to which they are applied) are printed correctly. See [Chromium bug 131054](https://crbug.com/131054)."\]

## See also

- WebKit [bug 64583](https://bugs.webkit.org/show_bug.cgi?id=64583): "WIP: Add CSS property to control printing of backgrounds for individual elements"
- CSSWG wiki: [print-backgrounds](https://wiki.csswg.org/ideas/print-backgrounds) - a proposal to standardize this property
- CSS Color Module Level 4: the `color-adjust` property - a newer proposal to standardize this property

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-print-color-adjust" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-print-color-adjust</a>
