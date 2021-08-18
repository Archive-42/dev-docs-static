# font-kerning

The `font-kerning` CSS property sets the use of the kerning information stored in a font.

Kerning defines how letters are spaced. In _well-kerned_ fonts, this feature makes character spacing more uniform and pleasant to read than it would otherwise be.

In the image below, for instance, the examples on the left do not use kerning, while the ones on the right do:

<img src="data:image/png;base64,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" alt="Example of font-kerning" width="318" height="222" />

## Syntax

The `font-kerning` property is specified as one of the keyword values listed below.

### Values

`auto`  
The browser determines whether font kerning should be used or not. For example, some browsers will disable kerning on small fonts, since applying it could harm the readability of text.

`normal`  
Font kerning information stored in the font must be applied.

`none`  
Font kerning information stored in the font is disabled.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | normal | none

## Examples

### Enabling and disabling kerning

#### HTML

    <div id="kern"></div>
    <div id="nokern"></div>
    <textarea id="input">AV T. ij</textarea>

#### CSS

    div {
      font-size: 2rem;
      font-family: serif;
    }

    #nokern {
      font-kerning: none;
    }

    #kern {
      font-kerning: normal;
    }

#### JavaScript

    let input  = document.getElementById('input');
    let kern   = document.getElementById('kern');
    let nokern = document.getElementById('nokern');

    input.addEventListener('keyup', function() {
      kern.textContent = input.value; /* Update content */
      nokern.textContent = input.value;
    });

    kern.textContent = input.value; /* Initialize content */
    nokern.textContent = input.value;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-3/#propdef-font-kerning">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-kerning' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`font-kerning`

33

29-33

79

32

No

20

16-20

9

6

4.4.3

4.4-4.4.3

33

29-33

32

20

16-20

9

6

2.0

1.0-2.0

## See also

- [`font-variant`](font-variant), [`font-variant-position`](font-variant-position), [`font-variant-east-asian`](font-variant-east-asian), [`font-variant-caps`](font-variant-caps), [`font-variant-ligatures`](font-variant-ligatures), [`font-variant-numeric`](font-variant-numeric), [`font-variant-alternates`](font-variant-alternates), [`font-synthesis`](font-synthesis), [`letter-spacing`](letter-spacing)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-kerning" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-kerning</a>
