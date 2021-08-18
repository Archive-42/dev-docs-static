# marks

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `marks` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [at-rule](../at-rule) descriptor, used with the [`@page`](../@page) at-rule, adds crop and/or cross marks to the presentation of the document. _Crop marks_ indicate where the page should be cut. _Cross marks_ are used to align sheets.

Crop marks and cross marks are printed outside the page box. To have room to show crop and cross marks, the final pages will have to be somewhat bigger than the page box.

## Syntax

    /* Keyword values */
    marks: none;
    marks: crop;
    marks: cross;
    marks: crop cross;

### Values

`crop`  
Crop marks will be displayed.

`cross`  
Cross marks will be displayed.

`none`  
No marks will be displayed.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@page"><code>@page</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    none | [ crop || cross ]

## Examples

### Adding crop and cross marks

    @page {
      marks: crop cross;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-page-3/#marks">CSS Paged Media Module Level 3<br />
<span class="small">The definition of 'marks' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

This CSS property was initially proposed in CSS Level 2, but was dropped from CSS Level 2 (Revision 1).

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

`marks`

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

- [`bleed`](bleed)
- [`size`](size)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@page/marks" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@page/marks</a>
