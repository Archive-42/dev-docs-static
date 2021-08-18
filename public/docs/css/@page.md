# @page

The `@page` CSS at-rule is used to modify some CSS properties when printing a document.

## Syntax

    @page {
      margin: 1cm;
    }

    @page :first {
      margin: 2cm;
    }

### Descriptors

[`size`](@page/size)  
Specifies the target size and orientation of the page box’s containing block. In the general case, where one page box is rendered onto one page sheet, it also indicates the size of the destination page sheet.

[`marks`](@page/marks)  
Adds crop and/or registration marks to the document.

[`bleed`](@page/bleed)  
Specifies the extent beyond the page box at which the page rendering is clipped.

## Description

You can't change all CSS properties with `@page`. You can only change the margins, orphans, widows, and page breaks of the document. Attempts to change any other CSS properties will be ignored.

The `@page` at-rule can be accessed via the CSS object model interface [`CSSPageRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPageRule).

**Note:** The W3C is discussing how to handle viewport-related [`<length>`](length) units, `vh`, `vw`, `vmin`, and `vmax`. Meanwhile do not use them within a `@page` at-rule.

## Formal syntax

    @page <page-selector-list> {
      <page-body>
    }where
    <page-selector-list> = [ <page-selector># ]?
    <page-body> = <declaration>? [ ; <page-body> ]? | <page-margin-box> <page-body>where
    <page-selector> = <pseudo-page>+ | <ident> <pseudo-page>*
    <page-margin-box> = <page-margin-box-type> '{' <declaration-list> '}'where
    <pseudo-page> = : [ left | right | first | blank ]
    <page-margin-box-type> = @top-left-corner | @top-left | @top-center | @top-right | @top-right-corner | @bottom-left-corner | @bottom-left | @bottom-center | @bottom-right | @bottom-right-corner | @left-top | @left-middle | @left-bottom | @right-top | @right-middle | @right-bottom

## Examples

### @page pseudo-class examples

Please refer to the various [pseudo-classes](pseudo-classes) of `@page` for examples.

- [`:blank`](:blank)
- [`:first`](:first)
- [`:left`](:left)
- [`:right`](:right)
- <span class="page-not-created">`:recto`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- <span class="page-not-created">`:verso`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#page">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of ':recto and :verso' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds the <code>:recto</code> and <code>:verso</code> page selectors</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-page-3/#at-page-rule">CSS Paged Media Module Level 3<br />
<span class="small">The definition of '@page' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change from <a href="https://www.w3.org/TR/CSS2/">CSS Level 2 (Revision 1)</a>, though more CSS at-rules can be used inside a <code>@page</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/page.html#page-selectors">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '@page' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`@page`

2

12

19

8

6

No

37

18

19

14

No

1.0

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

`page-margin-boxes`

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

`page-orientation`

85

85

No

No

71

No

85

85

No

60

No

No

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

## See also

- See the [\[META\] CSS Paged Media Module Level 3](https://bugzilla.mozilla.org/show_bug.cgi?id=286443) ticket in Bugzilla for tracking progress on the subject (page-based counters, etc.)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@page" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@page</a>
