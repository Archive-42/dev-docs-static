# font-variant-alternates

The `font-variant-alternates` CSS property controls the usage of alternate glyphs. These alternate glyphs may be referenced by alternative names defined in [`@font-feature-values`](@font-feature-values).

    /* Keyword values */
    font-variant-alternates: normal;
    font-variant-alternates: historical-forms;

    /* Functional notation values */
    font-variant-alternates: stylistic(user-defined-ident);
    font-variant-alternates: styleset(user-defined-ident);
    font-variant-alternates: character-variant(user-defined-ident);
    font-variant-alternates: swash(user-defined-ident);
    font-variant-alternates: ornaments(user-defined-ident);
    font-variant-alternates: annotation(user-defined-ident);
    font-variant-alternates: swash(ident1) annotation(ident2);

    /* Global values */
    font-variant-alternates: initial;
    font-variant-alternates: inherit;
    font-variant-alternates: unset;

The [`@font-feature-values`](@font-feature-values) at-rule can define names for alternative glyph functions (`stylistic`, `styleset`, `character-variant`, `swash`, `ornament` or `annotation`), associating the name with OpenType parameters. This property allows those human-readable names (defined in [`@font-feature-values`](@font-feature-values)) in the stylesheet.

## Syntax

This property may take one of two forms:

- either the keyword `normal`
- or one or more of the other keywords and functions listed below, space-separated, in any order.

### Values

`normal`  
This keyword deactivates alternate glyphs.

`historical-forms`  
This keyword enables historical forms — glyphs that were common in the past but not today. It corresponds to the OpenType value `hist`.

`stylistic()`  
This function enables stylistic alternates for individual characters. The parameter is a font-specific name mapped to a number. It corresponds to the OpenType value `salt`, like `salt 2`.

`styleset()`  
This function enables stylistic alternatives for sets of characters. The parameter is a font-specific name mapped to a number. It corresponds to the OpenType value `ssXY`, like `ss02`.

`character-variant()`  
This function enables specific stylistic alternatives for characters. It is similar to `styleset()`, but doesn't create coherent glyphs for a set of characters; individual characters will have independent and not necessarily coherent styles. The parameter is a font-specific name mapped to a number. It corresponds to the OpenType value `cvXY`, like `cv02`.

`swash()`  
This function enables [swash](https://en.wikipedia.org/wiki/Swash_%28typography%29) glyphs. The parameter is a font-specific name mapped to a number. It corresponds to the OpenType values `swsh` and `cswh`, like `swsh 2` and `cswh 2`.

`ornaments()`  
This function enables ornaments, like [fleurons](https://en.wikipedia.org/wiki/Fleuron_%28typography%29) and other dingbat glyphs. The parameter is a font-specific name mapped to a number. It corresponds to the OpenType value `ornm`, like `ornm 2`.

**Note:** In order to preserve text semantics, font designers should include ornaments that don't match Unicode dingbat characters as ornamental variants of the bullet character (U+2022). Be aware that some existing fonts don't follow this advice.

`annotation()`  
This function enables annotations, like circled digits or inverted characters. The parameter is a font-specific name mapped to a number. It corresponds to the OpenType value `nalt`, like `nalt 2`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | [ stylistic( <feature-value-name> ) || historical-forms || styleset( <feature-value-name># ) || character-variant( <feature-value-name># ) || swash( <feature-value-name> ) || ornaments( <feature-value-name> ) || annotation( <feature-value-name> ) ]where
    <feature-value-name> = <custom-ident>

## Examples

### HTML

    <p>Firefox rocks!</p>
    <p class="variant">Firefox rocks!</p>

### CSS

    @font-feature-values "Leitura Display Swashes" {
        @swash { fancy: 1 }
    }

    p {
      font-size: 1.5rem;
    }

    .variant {
      font-family: Leitura Display Swashes;
      font-variant-alternates: swash(fancy);
    }

### Result

**Note:** You need to install the OpenType font _Leitura Display Swashes_ for this example to work. You can find a few free versions for testing purposes, for example from [fontsgeek.com](https://fontsgeek.com/fonts/Leitura-Display-Swashes).

## Specifications

Not part of any standard.

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

`font-variant-alternates`

No

No

34

No

No

No

No

No

34

No

No

No

`annotation`

No

No

34

No

No

No

No

No

34

No

No

No

`character_variant`

No

No

34

No

No

No

No

No

34

No

No

No

`ornaments`

No

No

34

No

No

No

No

No

34

No

No

No

`styleset`

No

No

34

No

No

No

No

No

34

No

No

No

`stylistic`

No

No

34

No

No

No

No

No

34

No

No

No

`swash`

No

No

34

No

No

No

No

No

34

No

No

No

## See Also

- [`font-variant`](font-variant)
- [`font-variant-caps`](font-variant-caps)
- [`font-variant-east-asian`](font-variant-east-asian)
- [`font-variant-ligatures`](font-variant-ligatures)
- [`font-variant-numeric`](font-variant-numeric)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-alternates" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-alternates</a>
