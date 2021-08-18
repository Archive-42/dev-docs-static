# bleed

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `bleed` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [at-rule](../at-rule) descriptor, used with the [`@page`](../@page) at-rule, specifies the extent of the page bleed area outside the page box. This property only has effect if crop marks are enabled using the [`marks`](marks) property.

## Syntax

    /* Keyword values */
    bleed: auto;

    /* <length> values */
    bleed: 8pt;
    bleed: 1cm;

### Values

`auto`  
Computes to `6pt` if the value of [`marks`](marks) is `crop`. Otherwise it computes to zero.

`<length>`  
Specifies by how far outward, in each direction, the bleed area extends past the page box. Values may be negative, but there may be implementation-specific limits.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@page"><code>@page</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    auto | <length>

## Examples

### Setting a page bleed of 1cm

    @page {
      bleed: 1cm;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-page-3/#bleed">CSS Paged Media Module Level 3<br />
<span class="small">The definition of 'bleed' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`bleed`

No

No

No

No

No

No

No

No

No

No

No

No

## See also

- [`marks`](marks)
- [`size`](size)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@page/bleed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@page/bleed</a>
