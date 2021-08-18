# border-collapse

The `border-collapse` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether cells inside a [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) have shared or separate borders.

When cells are collapsed, the [`border-style`](border-style) value of `inset` behaves like `groove`, and `outset` behaves like `ridge`.

When cells are separated, the distance between cells is defined by the [`border-spacing`](border-spacing) property.

## Syntax

    /* Keyword values */
    border-collapse: collapse;
    border-collapse: separate;

    /* Global values */
    border-collapse: inherit;
    border-collapse: initial;
    border-collapse: unset;

The `border-collapse` property is specified as a single keyword, which may be chosen from the list below.

### Values

`collapse`  
Adjacent cells have shared borders (the collapsed-border table rendering model).

`separate`  
Adjacent cells have distinct borders (the separated-border table rendering model).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>separate</code></td></tr><tr class="even"><td>Applies to</td><td><code>table</code> and <code>inline-table</code> elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    collapse | separate

## Examples

### A colorful table of browser engines

#### HTML

    <table class="separate">
      <caption><code>border-collapse: separate</code></caption>
      <tbody>
        <tr><th>Browser</th> <th>Layout Engine</th></tr>
        <tr><td class="fx">Firefox</td> <td class="gk">Gecko</td></tr>
        <tr><td class="ed">Edge</td> <td class="tr">EdgeHTML</td></tr>
        <tr><td class="sa">Safari</td> <td class="wk">Webkit</td></tr>
        <tr><td class="ch">Chrome</td> <td class="bk">Blink</td></tr>
        <tr><td class="op">Opera</td> <td class="bk">Blink</td></tr>
      </tbody>
    </table>
    <table class="collapse">
      <caption><code>border-collapse: collapse</code></caption>
      <tbody>
        <tr><th>Browser</th> <th>Layout Engine</th></tr>
        <tr><td class="fx">Firefox</td> <td class="gk">Gecko</td></tr>
        <tr><td class="ed">Edge</td> <td class="tr">EdgeHTML</td></tr>
        <tr><td class="sa">Safari</td> <td class="wk">Webkit</td></tr>
        <tr><td class="ch">Chrome</td> <td class="bk">Blink</td></tr>
        <tr><td class="op">Opera</td> <td class="bk">Blink</td></tr>
      </tbody>
    </table>

#### CSS

    .collapse {
      border-collapse: collapse;
    }

    .separate {
      border-collapse: separate;
    }

    table {
      display: inline-table;
      margin: 1em;
      border: dashed 5px;
    }

    table th,
    table td {
      border: solid 3px;
    }

    .fx { border-color: orange blue; }
    .gk { border-color: black red; }
    .ed { border-color: blue gold; }
    .tr { border-color: aqua; }
    .sa { border-color: silver blue; }
    .wk { border-color: gold blue; }
    .ch { border-color: red yellow green blue; }
    .bk { border-color: navy blue teal aqua; }
    .op { border-color: red; }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/tables.html#borders">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'border-collapse' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-collapse`

1

12

1

5

4

1.2

2.3

18

4

10.1

3

1.0

## See also

- [`border-spacing`](border-spacing), [`border-style`](border-style)
- The `border-collapse` property alters the appearance of the [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) HTML element.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse</a>
