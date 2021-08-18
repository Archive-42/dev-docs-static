# page-break-before

This property has been replaced by the [`break-before`](break-before) property.

The `page-break-before` CSS property adjusts page breaks _before_ the current element.

This property applies to block elements that generate a box. It won't apply on an empty [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) that won't generate a box.

    /* Keyword values */
    page-break-before: auto;
    page-break-before: always;
    page-break-before: avoid;
    page-break-before: left;
    page-break-before: right;
    page-break-before: recto;
    page-break-before: verso;

    /* Global values */
    page-break-before: inherit;
    page-break-before: initial;
    page-break-before: unset;

## Syntax

### Values

`auto`  
Initial value. Automatic page breaks (neither forced nor forbidden).

`always`  
Always force page breaks before the element.

`avoid`  
Avoid page breaks before the element.

`left`  
Force page breaks before the element so that the next page is formatted as a left page.

`right`  
Force page breaks before the element so that the next page is formatted as a right page.

`recto` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
If pages progress left-to-right, then this acts like `right`. If pages progress right-to-left, then this acts like `left`.

`verso` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
If pages progress left-to-right, then this acts like `left`. If pages progress right-to-left, then this acts like `right`.

## Page break aliases

The `page-break-before` property is now a legacy property, replaced by [`break-before`](break-before).

For compatibility reasons, `page-break-before` should be treated by browsers as an alias of `break-before`. This ensures that sites using `page-break-before` continue to work as designed. A subset of values should be aliased as follows:

<table><thead><tr class="header"><th>page-break-before</th><th>break-before</th></tr></thead><tbody><tr class="odd"><td><code>auto</code></td><td><code>auto</code></td></tr><tr class="even"><td><code>left</code></td><td><code>left</code></td></tr><tr class="odd"><td><code>right</code></td><td><code>right</code></td></tr><tr class="even"><td><code>avoid</code></td><td><code>avoid</code></td></tr><tr class="odd"><td><code>always</code></td><td><code>page</code></td></tr></tbody></table>

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>block-level elements in the normal flow of the root element. User agents may also apply it to other elements like <code>table-row</code> elements.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | always | avoid | left | right | recto | verso

## Examples

### Avoid a page break before an element

    /* avoid page break before div elements of class note */
    div.note {
        page-break-before: avoid;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#page">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'recto and verso' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds the values <code>recto</code> and <code>verso</code>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-page-3/#page-break-before">CSS Paged Media Module Level 3<br />
<span class="small">The definition of 'page-break-before' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Extends the element that this property applies to table rows and table row groups.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/page.html#propdef-page-break-before">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'page-break-before' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`page-break-before`

1

12

1

The values `avoid`, `left`, and `right` are unsupported.

4

7

1.2

37

18

4

The values `avoid`, `left`, and `right` are unsupported.

14

1

1.0

## See also

- [`break-before`](break-before), [`break-after`](break-after), [`break-inside`](break-inside)
- [`page-break-after`](page-break-after), [`page-break-inside`](page-break-inside)
- [`orphans`](orphans), [`widows`](widows)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/page-break-before" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/page-break-before</a>
