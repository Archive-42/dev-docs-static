# column-fill

The `column-fill` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property controls how an element's contents are balanced when broken into columns.

## Syntax

    /* Keyword values */
    column-fill: auto;
    column-fill: balance;
    column-fill: balance-all;

    /* Global values */
    column-fill: inherit;
    column-fill: initial;
    column-fill: unset;

The `column-fill` property is specified as one of the keyword values listed below. The initial value is `balance` so the content will be balanced across the columns.

### Values

`auto`  
Columns are filled sequentially. Content takes up only the room it needs, possibly resulting in some columns remaining empty.

`balance`  
Content is equally divided between columns. In fragmented contexts, such as [paged media](https://developer.mozilla.org/en-US/docs/Web/CSS/Paged_Media), only the last fragment is balanced. Therefore in paged media, only the last page would be balanced.

`balance-all`  
Content is equally divided between columns. In fragmented contexts, such as [paged media](https://developer.mozilla.org/en-US/docs/Web/CSS/Paged_Media), all fragments are balanced.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>balance</code></td></tr><tr class="even"><td>Applies to</td><td>multicol elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | balance | balance-all

## Example

### Balancing column content

#### HTML

    <p class="fill-auto">
      This paragraph fills columns one at a time. Since all of the text can fit in the first column, the others are empty.
    </p>

    <p class="fill-balance">
      This paragraph attempts to balance the amount of content in each column.
    </p>

#### CSS

    p {
      height: 7em;
      background: #ff9;
      columns: 3;
      column-rule: 1px solid;
    }

    p.fill-auto {
      column-fill: auto;
    }

    p.fill-balance {
      column-fill: balance;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-multicol-1/#cf">CSS Multi-column Layout Module<br />
<span class="small">The definition of 'column-fill' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`column-fill`

50

12

52

13-74

10

37

9

8

50

50

52

14

37

9

8

5.0

`balance-all`

No

See [bug 909596](https://crbug.com/909596)

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

Note that there are some interoperability issues and bugs with `column-fill` across browsers, due to unresolved issues in the specification.

In particular, when using `column-fill: auto` to fill columns sequentially, Chrome will only consult this property if the multicol container has a size in the block dimension (e.g., height in a horizontal writing mode). Firefox will always consult this property, therefore filling the first column with all of the content in cases where there is no size.

## See also

- [Multiple-column Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
- [`column-count`](column-count)
- [`column-width`](column-width)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-fill" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/column-fill</a>
