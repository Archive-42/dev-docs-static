# Column combinator

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The **column combinator** (`||`) is placed between two CSS selectors. It matches only those elements matched by the second selector that belong to the column elements matched by the first.

    /* Table cells that belong to the "selected" column */
    col.selected || td {
      background: gray;
    }

## Syntax

    column-selector || cell-selector {
      /* style properties */
    }

## Examples

### HTML

    <table border="1">
      <colgroup>
        <col span="2"/>
        <col class="selected"/>
      </colgroup>
      <tbody>
        <tr>
          <td>A
          <td>B
          <td>C
        </tr>
        <tr>
          <td colspan="2">D</td>
          <td>E</td>
        </tr>
        <tr>
          <td>F</td>
          <td colspan="2">G</td>
        </tr>
      </tbody>
    </table>

### CSS

    col.selected || td {
      background: gray;
      color: white;
      font-weight: bold;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#the-column-combinator">Selectors Level 4<br />
<span class="small">The definition of 'column combinator' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Column_combinator`

No

No

No

See [bug 1605558](https://bugzil.la/1605558).

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

- [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col)
- [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup)
- [`grid`](grid)
- [`:nth-col`](:nth-col)
- [`:nth-last-col`](:nth-last-col)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Column_combinator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Column_combinator</a>
