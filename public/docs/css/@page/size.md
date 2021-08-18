# size

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `size` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [at-rule](../at-rule) descriptor, used with the [`@page`](../@page) at-rule, defines the size and orientation of the box which is used to represent a page. Most of the time, this size corresponds to the target size of the printed page if applicable.

Size may either be defined with a "scalable" keyword (in this case the page will fill the available dimensions) or with absolute dimensions.

## Syntax

    /* Keyword values for scalable size */
    size: auto;
    size: portrait;
    size: landscape;

    /* <length> values */
    /* 1 value: height = width */
    size: 6in;

    /* 2 values: width then height */
    size: 4in 6in;

    /* Keyword values for absolute size */
    size: A4;
    size: B5;
    size: JIS-B4;
    size: letter;

    /* Mixing size and orientation */
    size: A4 portrait;

### Values

`auto`  
The user agent decides the size of the page. In most cases, the dimensions and orientation of the target sheet are used.

`landscape`  
The content of the page is displayed in landscape mode (i.e. the longest side of the box is horizontal).

`portrait`  
The content of the page is displayed in portrait mode (i.e. the longest side of the box is vertical). This is the default orientation.

`<length>`  
Any length value (see [`<length>`](../length)). The first value corresponds to the width of the page box and the second one corresponds to its height. If only one value is provided, it is used for both width and height.

`<page-size>`  
A5  
This matches the standard, ISO dimensions: 148mm x 210mm.

A4  
This matches the standard, ISO dimensions: 210mm x 297mm. (most frequently used dimensions for personal printing.)

A3  
This matches the standard, ISO dimensions: 297mm x 420mm.

B5  
This matches the standard, ISO dimensions: 176mm x 250mm.

B4  
This matches the standard, ISO dimensions: 250mm x 353mm.

JIS-B5  
This correspond to the JIS standard dimensions: 182mm x 257mm.

JIS-B4  
This correspond to the JIS standard dimensions: 257mm x 364mm.

letter  
This keyword is a equivalent to the dimensions of letter paper in North America i.e. 8.5in x 11in.

legal  
This keyword is a equivalent to the dimensions of legal papers in North America i.e. 8.5in x 14in.

ledger  
This keyword is a equivalent to the dimensions of ledger pages in North America i.e. 11in x 17in.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@page"><code>@page</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr></tbody></table>

## Formal syntax

    <length>{1,2} | auto | [ <page-size> || [ portrait | landscape ] ]where
    <page-size> = A5 | A4 | A3 | B5 | B4 | JIS-B5 | JIS-B4 | letter | legal | ledger

## Examples

### Specifying size and orientation

    @page {
      size: 4in 6in landscape;
    }

### Nesting inside a @media rule

    @media print {
      @page {
        size: 50mm 150mm;
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-page-3/#page-size-prop">CSS Paged Media Module Level 3<br />
<span class="small">The definition of 'size' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`size`

15

79

No

No

15

No

37

18

No

14

No

1.5

`jis-b4`

83

83

No

No

69

No

83

83

No

59

No

13.0

`jis-b5`

83

83

No

No

69

No

83

83

No

59

No

13.0

## See also

- [`bleed`](bleed)
- [`marks`](marks)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@page/size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@page/size</a>
