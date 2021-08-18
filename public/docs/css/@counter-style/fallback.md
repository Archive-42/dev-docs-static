# fallback

The `fallback` descriptor can be used to specify a counter style to fall back to if the current counter style cannot create a marker representation for a particular counter value.

## Syntax

    /* Keyword values */
    fallback: lower-alpha;
    fallback: custom-gangnam-style;

## Description

If the specified fallback style is also unable to construct a representation, then its fallback style will be used. If a valid fallback style is not specified, it defaults to `decimal`.

A couple of scenarios where a fallback style will be used are:

- When the [`range`](range) descriptor is specified for a counter style, the fallback style will be used to represent values that fall outside the range.
- When the `fixed` [`system`](system) is used and there are not enough symbols to cover all the list items, the fallback style will be used for the rest of the list items.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@counter-style"><code>@counter-style</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>decimal</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    <counter-style-name>where
    <counter-style-name> = <custom-ident>

## Examples

### Specifying a fallback counter style

#### HTML

    <ul class="list">
      <li>One</li>
      <li>Two</li>
      <li>Three</li>
      <li>Four</li>
      <li>Five</li>
    </ul>

#### CSS

    @counter-style fallback-example {
      system: fixed; symbols: "\24B6" "\24B7" "\24B8";
      fallback: upper-alpha;
    }

    .list {
      list-style: fallback-example;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-counter-styles-3/#counter-style-fallback">CSS Counter Styles Level 3<br />
<span class="small">The definition of 'fallback' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

- [`list-style`](../list-style), [`list-style-image`](../list-style-image), [`list-style-position`](../list-style-position)
- [`symbols()`](<../symbols()>): the functional notation creating anonymous counter styles

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/fallback" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/fallback</a>
