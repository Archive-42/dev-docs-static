# :right

The `:right` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes), used with the [`@page`](@page) [at-rule](at-rule), represents all right-hand pages of a printed document.

    /* Selects any right-hand pages when printing */
    @page :right {
      margin: 2in 3in;
    }

Whether a given page is "left" or "right" is determined by the major writing direction of the document. For example, if the first page has a major writing direction of left-to-right then it will be a `:right` page; if it has a major writing direction of right-to-left then it will be a [`:left`](:left) page.

**Note:** This pseudo-class can be used to change only the [`margin`](margin), [`padding`](padding), [`border`](border), and [`background`](background) properties of the _page box_. All other properties will be ignored, and only the page box, not the document content on the page, will be affected.

## Syntax

    :right

## Examples

### Setting margins for right-hand pages

    @page :right {
      margin: 2in 3in;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-page-3/#left-right-first">CSS Paged Media Module Level 3<br />
<span class="small">The definition of ':right' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/page.html#page-selectors">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of ':right' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:right`

6

12

No

8

9.2

5.1

≤37

18

No

10.1

6

1.0

## See also

- [`@page`](@page)
- Other page-related pseudo-classes: [`:first`](:first), [`:left`](:left)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:right" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:right</a>
