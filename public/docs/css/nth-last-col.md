# :nth-last-col

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `:nth-last-col()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) is designed for tables and grids. It accepts the An+B notation such as used with the [`:nth-child`](:nth-child) selector, using this to target every nth column before it, therefore counting back from the end of the set of columns. The values odd and even are also valid.

    /* Selects every odd column in a table */
    :nth-last-col(odd) {
      background-color: pink;
    }

## Syntax

The `nth-last-col` pseudo-class is specified with a single argument, which represents the pattern for matching elements.

See [`:nth-child`](:nth-child) for a more detailed explanation of its syntax.

### Formal syntax

    :nth-last-col

## Examples

### Basic example

#### HTML

    <table>
      <tr>
        <td>one</td>
        <td>two</td>
        <td>three</td>
        <td>four</td>
      </tr>
      <tr>
      <td>one</td>
        <td>two</td>
        <td>three</td>
        <td>four</td>
      </tr>
    </table>

#### CSS

    td {
      border: 1px solid #ccc;
      padding: .2em;
    }

    /* Odd columns starting with the final column of the table */
    :nth-last-col(2n+1) {
      background-color: pink;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#the-nth-last-col-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':nth-last-col' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.selectors.nth-last-col`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

The compatibility table on this page is generated from structured data. If you'd like to contribute to the data, please check out <https://github.com/mdn/browser-compat-data> and send us a pull request.

## See also

- [`:nth-child`](:nth-child), [`:nth-last-of-type`](:nth-last-of-type)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-col" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-col</a>
