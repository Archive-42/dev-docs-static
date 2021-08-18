# @counter-style

The `@counter-style` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [at-rule](at-rule) lets you define counter styles that are not part of the predefined set of styles. A `@counter-style` rule defines how to convert a counter value into a string representation.

    @counter-style thumbs {
      system: cyclic;
      symbols: "\1F44D";
      suffix: " ";
    }

    ul {
      list-style: thumbs;
    }

The initial version of CSS defined a set of useful counter styles. However, although more styles were added to this set of predefined styles over the years, this system proved too restrictive to fulfill the needs of worldwide typography. The `@counter-style` at-rule addresses this shortcoming in an open-ended manner, by allowing authors to define their own counter styles when the pre-defined styles aren't fitting their needs.

## Syntax

### Descriptors

Each `@counter-style` is identified by a name and has a set of descriptors.

[`system`](@counter-style/system)  
Specifies the algorithm to be used for converting the integer value of a counter to a string representation.

<!-- -->

[`negative`](@counter-style/negative)  
Lets the author specify symbols to be appended or prepended to the counter representation if the value is negative.

<!-- -->

[`prefix`](@counter-style/prefix)  
Specifies a symbol that should be prepended to the marker representation. Prefixes are added to the representation in the final stage, so in the final representation of the counter, it comes before the negative sign.

<!-- -->

[`suffix`](@counter-style/suffix)  
Specifies, similar to the prefix descriptor, a symbol that is appended to the marker representation. Suffixes come after the marker representation.

<!-- -->

[`range`](@counter-style/range)  
Defines the range of values over which the counter style is applicable. If a counter style is used to represent a counter value outside of its ranges, the counter style will drop back to its fallback style.

<!-- -->

[`pad`](@counter-style/pad)  
Is used when you need the marker representations to be of a minimum length. For example if you want the counters to start at 01 and go through 02, 03, 04 etc, then the pad descriptor is to be used. For representations larger than the specified pad value, the marker is constructed as normal.

<!-- -->

[`fallback`](@counter-style/fallback)  
Specifies a system to fall back into if either the specified system is unable to construct the representation of a counter value or if the counter value outside the specified range. If the specified fallback also fails to represent the value, then the fallback style's fallback is used, if one is specified. If there are either no fallback systems described or if the chain of fallback systems are unable to represent a counter value, then it will ultimately fall back to the decimal style.

<!-- -->

[`symbols`](@counter-style/symbols)  
Specifies the symbols that are to be used for the marker representations. Symbols can contain string, images or custom identifiers. How the symbols are used to construct the marker representation is up to the algorithm specified in the system descriptor. For example, if the system specified is fixed, then each of the N symbols specified in the descriptor will be used to represent the first N counter symbols. Once the specified set of symbols have exhausted, the fallback style will be used for the rest of the list.

The below `@counter-style` rule uses images instead of character symbols. Image values for symbols is currently an 'at risk' feature, and is not implemented in any browser.

    @counter-style winners-list {
      system: fixed;
      symbols: url(gold-medal.svg) url(silver-medal.svg) url(bronze-medal.svg);
      suffix: " ";
    }

<!-- -->

[`additive-symbols`](@counter-style/additive-symbols)  
While the symbols specified in the symbols descriptor is used for constructing marker representation by most algorithms, some systems such as 'additive' rely on _additive tuples_ described in this descriptor. Each additive tuple consists of a counter symbol and a non negative integer weight. The additive tuples must be specified in the descending order of their weights.

<!-- -->

[`speak-as`](@counter-style/speak-as)  
Describes how to read out the counter style in speech synthesizers, such as screen readers. For example, the value of the marker symbol can be read out as numbers or alphabets for ordered lists or as audio cues for unordered lists, based on the value of this descriptor.

## Formal syntax

    @counter-style <counter-style-name> {
      [ system: <counter-system>; ] ||
      [ symbols: <counter-symbols>; ] ||
      [ additive-symbols: <additive-symbols>; ] ||
      [ negative: <negative-symbol>; ] ||
      [ prefix: <prefix>; ] ||
      [ suffix: <suffix>; ] ||
      [ range: <range>; ] ||
      [ pad: <padding>; ] ||
      [ speak-as: <speak-as>; ] ||
      [ fallback: <counter-style-name>; ]
    }where
    <counter-style-name> = <custom-ident>

## Examples

### Specifying symbols with counter-style

    @counter-style circled-alpha {
      system: fixed;
      symbols: Ⓐ Ⓑ Ⓒ Ⓓ Ⓔ Ⓕ Ⓖ Ⓗ Ⓘ Ⓙ Ⓚ Ⓛ Ⓜ Ⓝ Ⓞ Ⓟ Ⓠ Ⓡ Ⓢ Ⓣ Ⓤ Ⓥ Ⓦ Ⓧ Ⓨ Ⓩ;
      suffix: " ";
    }

The above counter style rule can be applied to lists like this:

    .items {
      list-style: circled-alpha;
    }

Which will produce lists like this:

Ⓐ One  
Ⓑ Two  
Ⓒ Three  
Ⓓ Four  
Ⓔ FIve  
...  
...  
Ⓨ Twenty Five  
Ⓩ Twenty Six  
27 Twenty Seven  
28 Twenty Eight  
29 Twenty Nine  
30 Thirty

See more examples on the [demo page](https://mdn.github.io/css-examples/counter-style-demo/).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-counter-styles-3/#the-counter-style-rule">CSS Counter Styles Level 3<br />
<span class="small">The definition of 'counter-style' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`@counter-style`

No

No

33

No

No

No

No

No

33

No

No

No

`additive-symbols`

No

No

33

No

No

No

No

No

33

No

No

No

`fallback`

No

No

33

No

No

No

No

No

33

No

No

No

`negative`

No

No

33

No

No

No

No

No

33

No

No

No

`pad`

No

No

33

No

No

No

No

No

33

No

No

No

`prefix`

No

No

33

No

No

No

No

No

33

No

No

No

`range`

No

No

33

No

No

No

No

No

33

No

No

No

`speak-as`

No

No

33

No

No

No

No

No

33

No

No

No

`suffix`

No

No

33

No

No

No

No

No

33

No

No

No

`symbols`

No

No

33

No

No

No

No

No

33

No

No

No

`system`

No

No

33

No

No

No

No

No

33

No

No

No

### Quantum CSS notes

- Gecko allowed `none` as a value of the `system` and `fallback` descriptors of `@counter-style`, which as per spec should result in an invalid at-rule. Firefox's new parallel CSS engine (also known as [Quantum CSS](https://wiki.mozilla.org/Quantum) or [Stylo](https://wiki.mozilla.org/Quantum/Stylo), released in Firefox 57) fixed this ([bug 1377414](https://bugzilla.mozilla.org/show_bug.cgi?id=1377414)).

## See also

- [`list-style`](list-style), [`list-style-image`](list-style-image), [`list-style-position`](list-style-position), [`list-style-type`](list-style-type)
- [`symbols()`](<symbols()>), the functional notation creating anonymous counter styles.
- CSS [`counter()`](<counter()>) and [`counters()`](<counters()>) functions
- [Counter style demo](https://mdn.github.io/css-examples/counter-style-demo/) ([code](https://github.com/mdn/css-examples/tree/master/counter-style-demo))

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style</a>
