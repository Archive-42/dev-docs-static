# caption-side

The `caption-side` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property puts the content of a table's [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption) on the specified side. The values are relative to the [`writing-mode`](writing-mode) of the table.

## Syntax

    /* Directional values */
    caption-side: top;
    caption-side: bottom;

    /* Logical values */
    caption-side: block-start;
    caption-side: block-end;
    caption-side: inline-start;
    caption-side: inline-end;

    /* Global values */
    caption-side: inherit;
    caption-side: initial;
    caption-side: unset;

The `caption-side` property is specified as one of the keyword values listed below.

### Values

`top`  
The caption box should be positioned above the table.

`bottom`  
The caption box should be positioned below the table.

`block-start`  
The caption box should be positioned at the block start edge of the table.

`block-end`  
The caption box should be positioned at the block end edge of the table.

`inline-start`  
The caption box should be positioned at the inline start edge of the table.

`inline-end`  
The caption box should be positioned at the inline end edge of the table.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>top</code></td></tr><tr class="even"><td>Applies to</td><td>table-caption elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    top | bottom | block-start | block-end | inline-start | inline-end

## Examples

### Setting captions above and below

#### HTML

    <table class="top">
      <caption>Caption ABOVE the table</caption>
      <tr>
        <td>Some data</td>
        <td>Some more data</td>
      </tr>
    </table>

    <br>

    <table class="bottom">
      <caption>Caption BELOW the table</caption>
      <tr>
        <td>Some data</td>
        <td>Some more data</td>
      </tr>
    </table>

#### CSS

    .top caption {
      caption-side: top;
    }

    .bottom caption {
      caption-side: bottom;
    }

    table {
      border: 1px solid red;
    }

    td {
      border: 1px solid blue;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#caption-side">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'caption-side' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Defines the <code>top</code> and <code>bottom</code> values as relative to the <code>writing-mode</code> value.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/tables.html#caption-position">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'caption-side' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`caption-side`

1

12

1

8

4

1

≤37

18

4

14

1

1.0

`non_standard_values`

No

No

1-87

No

No

No

No

No

4-87

No

No

No

`writing-mode_relative_values`

No

No

42

No

No

No

No

No

42

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/caption-side" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/caption-side</a>
