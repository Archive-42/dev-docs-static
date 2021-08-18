# HTMLImageElement.y

The read-only [`HTMLImageElement`](../htmlimageelement) property `y` indicates the y-coordinate of the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element's top border edge relative to the root element's origin.

The [`x`](x) and `y` properties are only valid for an image if its [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property has the computed value `table-column` or `table-column-group`. In other words: it has either of those values set explicitly on it, or it has inherited it from a containing element, or by being located within a column described by either [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col) or [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup).

## Syntax

    let imageY = htmlImageElement.y;

### Value

An integer value indicating the distance in pixels from the top edge of the element's nearest root element to the top edge of the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element's border box. The nearest root element is the outermost [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element that contains the image. If the image is in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), its `y` is relative to that frame.

In the diagram below, the top border edge is the top edge of the blue padding area. So the value returned by `y` would be the distance from that point to the top edge of the content area.

<img src="data:image/png;base64,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" alt="Diagram showing the relationships between the various boxes associated with an element" width="548" height="384" />

**Note:** The `y` property is only valid if the computed value of the image's [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property is either `table-column` or `table-column-group`; in other words, either of those are set directly on the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) or they're inherited from a containing element or by being located within a column described by either [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col) or [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup).

## Example

The example below demonstrates the use of the `HTMLImageElement` properties [`x`](x) and [`y`](y).

### HTML

In this example, we see a table showing information about users of a web site, including their user ID, their full name, and their avatar image.

    <table id="userinfo">
      <colgroup>
        <col span="2" class="group1">
        <col>
      </colgroup>
      <tr>
        <th>UserID</th>
        <th>Name</th>
        <th>Avatar</th>
      </tr>
      <tr>
        <td>12345678</td>
        <td>Johnny Rocket</td>
        <td><img src="https://interactive-examples.mdn.mozilla.net/media/examples/grapefruit-slice-332-332.jpg"</td>
      </th>
    </table>
    <pre id="log">
    </pre>

### JavaScript

The JavaScript code that fetches the image from the table and looks up its `x` and `y` values is below.

    let logBox = document.querySelector("pre");
    let tbl = document.getElementById("userinfo")

    let log = msg => {
      logBox.innerHTML += `${msg}<br>`;
    }

    let cell = tbl.rows[1].cells[2];
    let image = cell.querySelector("img");

    log(`Image's global X: ${image.x}`);
    log(`Image's global Y: ${image.y}`);

This uses the [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)'s [`rows`](../htmltableelement/rows) property to get a list of the rows in the table, from which it looks up row 1 (which, being a zero-based index, means the second row from the top). Then it looks at that [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr) (table row) element's <span class="page-not-created">`cells`</span> property to get a list of the cells in that row. The third cell is taken from that row (once again, specifying 2 as the zero-based offset).

From there, we can get the `<img>` element itself from the cell by calling [`querySelector()`](../element/queryselector) on the [`HTMLTableCellElement`](../htmltablecellelement) representing that cell.

Finally, we can look up and display the values of the `HTMLImageElement`'s `x` and `y` properties.

### CSS

The CSS defining the appearance of the table:

    .group1 {
      background-color: #d7d9f2;
    }

    table {
      border-collapse: collapse;
      border: 2px solid rgb(100, 100, 100);
      font-family: sans-serif;
    }

    td, th {
      border: 1px solid rgb(100, 100, 100);
      padding: 10px 14px;
    }

    td > img {
      max-width: 4em;
    }

### Result

The resulting table looks like this:

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-htmlimageelement-y">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'HTMLImageElement.y' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`y`

1

12

14

1-7

No

≤12.1

3

1

Yes

14

4-7

≤12.1

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/y" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/y</a>
