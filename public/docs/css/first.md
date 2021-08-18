# :first

The `:first` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes), used with the [`@page`](@page) [at-rule](at-rule), represents the first page of a printed document. (See [`:first-child`](:first-child) for general first element of a node.)

    /* Selects the first page when printing */
    @page :first {
      margin-left: 50%;
      margin-top: 50%;
    }

**Note:** You can't change all CSS properties with this pseudo-class. You can only change the margins, [`orphans`](orphans), [`widows`](widows), and page breaks of the document. Furthermore, you may only use [absolute-length](length#absolute_length_units) units when defining the margins. All other properties will be ignored.

## Syntax

    :first

## Examples

### HTML

    <p>First Page.</p>
    <p>Second Page.</p>
    <button>Print!</button>

### CSS

    @page :first {
      margin-left: 50%;
      margin-top: 50%;
    }

    p {
      page-break-after: always;
    }

### JavaScript

    document.querySelector("button").addEventListener('click', () => {
      window.print();
    });

### Result

Press the "Print!" button to print the example. The words on the first page should be somewhere around the center, while other pages will have their contents at the default position.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-page-3/#left-right-first">CSS Paged Media Module Level 3<br />
<span class="small">The definition of ':first' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/page.html#page-selectors">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of ':first' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:first`

18

12

No

8

9.2

6

4.4

18

No

10.1

6

1.0

## See also

- [`@page`](@page)
- Other page-related pseudo-classes: [`:left`](:left), [`:right`](:right)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:first" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:first</a>
