# :local-link

The `:local-link` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents an link to the same document. Therefore an element that is the source anchor of a hyperlink whose target’s absolute URL matches the element’s own document URL.

    /* Selects any <a> that links to the current document */
    a:local-link {
      color: green;
    }

## Syntax

    :local-link

## Examples

### HTML

    <a href="#target">This is a link on the current page.</a><br>
    <a href="https://example.com">This is an external link</a><br>

### CSS

    a:local-link {
      color: green;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#the-local-link-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':local-link' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.selectors.local-link`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

The compatibility table on this page is generated from structured data. If you'd like to contribute to the data, please check out <https://github.com/mdn/browser-compat-data> and send us a pull request.

## See also

- Link-related pseudo-classes: [`:link`](:link),[`:visited`](:visited), [`:hover`](:hover), [`:active`](:active)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:local-link" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:local-link</a>
