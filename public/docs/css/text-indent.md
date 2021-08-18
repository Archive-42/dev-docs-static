# text-indent

The `text-indent` CSS property sets the length of empty space (indentation) that is put before lines of text in a block.

Horizontal spacing is with respect to the left (or right, for right-to-left layout) edge of the containing block-level element's content box.

## Syntax

    /* <length> values */
    text-indent: 3mm;
    text-indent: 40px;

    /* <percentage> value
       relative to the containing block width */
    text-indent: 15%;

    /* Keyword values */
    text-indent: 5em each-line;
    text-indent: 5em hanging;
    text-indent: 5em hanging each-line;

    /* Global values */
    text-indent: inherit;
    text-indent: initial;
    text-indent: unset;

### Values

[`<length>`](length)  
Indentation is specified as an absolute [`<length>`](length). Negative values are allowed. See [`<length>`](length) values for possible units.

[`<percentage>`](percentage)  
Indentation is a [`<percentage>`](percentage) of the containing block's width.

`each-line` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Indentation affects the first line of the block container as well as each line after a _forced line break_, but does not affect lines after a _soft wrap break_.

`hanging` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Inverts which lines are indented. All lines _except_ the first line will be indented.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>block containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>the percentage as specified or the absolute length, plus any keywords as specified</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <length-percentage> && hanging? && each-line?where
    <length-percentage> = <length> | <percentage>

## Examples

### Simple indent

#### HTML

    <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy
        nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.</p>
    <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy
        nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.</p>

#### CSS

    p {
      text-indent: 5em;
      background: powderblue;
    }

#### Result

### Skipping indentation on the first paragraph

A common typographic practice when paragraph indentation is present is to skip the indentation for the first paragraph. As the _The Chicago Manual of Style_ puts it, “the first line of text following a subhead may begin flush left or be indented by the usual paragraph indention.”

Treating first paragraphs differently from subsequent paragraphs can be done using the [adjacent sibling combinator](adjacent_sibling_combinator), as in the following example:

#### HTML

    <h2>Lorem ipsum</h2>

    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse eu
    venenatis quam. Vivamus euismod eleifend metus vitae pharetra. In vel tempor metus.
    Donec dapibus feugiat euismod. Vivamus interdum tellus dolor. Vivamus blandit eros
    et imperdiet auctor. Mauris sapien nunc, condimentum a efficitur non, elementum ac
    sapien. Cras consequat turpis non augue ullamcorper, sit amet porttitor dui
    interdum.</p>

    <p>Sed laoreet luctus erat at rutrum. Proin velit metus, luctus in sapien in,
    tincidunt mattis ex. Praesent venenatis orci at sagittis eleifend. Nulla facilisi.
    In feugiat vehicula magna iaculis vehicula. Nulla suscipit tempor odio a semper.
    Donec vitae dapibus ipsum. Donec libero purus, convallis eu efficitur id, pulvinar
    elementum diam. Maecenas mollis blandit placerat. Ut gravida pellentesque nunc, in
    eleifend ante convallis sit amet.</p>

    <h2>Donec ullamcorper elit nisl</h2>

    <p>Donec ullamcorper elit nisl, sagittis bibendum massa gravida in. Fusce
    tempor in ante gravida iaculis. Integer posuere tempor metus. Vestibulum lacinia,
    nunc et dictum viverra, urna massa aliquam tellus, id mollis sem velit vestibulum
    nulla. Pellentesque habitant morbi tristique senectus et netus et malesuada fames
    ac turpis egestas. Donec vulputate leo ut iaculis ultrices. Cras egestas rhoncus
    lorem. Nunc blandit tempus lectus, rutrum hendrerit orci eleifend id. Ut at quam
    velit.</p>

    <p>Aenean rutrum tempor ligula, at luctus ligula auctor vestibulum. Sed
    sollicitudin velit in leo fringilla sollicitudin. Proin eu gravida arcu. Nam
    iaculis malesuada massa, eget aliquet turpis sagittis sed. Sed mollis tellus ac
    dui ullamcorper, nec lobortis diam pellentesque. Quisque dapibus accumsan libero,
    sed euismod ipsum ullamcorper sed.</p>

#### CSS

    p {
        text-align: justify;
        margin: 1em 0 0 0;
    }
    p + p {
        text-indent: 2em;
        margin: 0;
    }

#### Result

### Percentage indent

#### HTML

    <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy
        nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.</p>
    <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy
        nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.</p>

#### CSS

    p {
      text-indent: 30%;
      background: plum;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#text-indent-property">CSS Text Module Level 3<br />
<span class="small">The definition of 'text-indent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds the <code>hanging</code> and <code>each-line</code> keywords.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/text.html#indentation-prop">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'text-indent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The behavior with <code>display: inline-block</code> and anonymous block boxes is explicitly defined.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#text-indent">CSS Level 1<br />
<span class="small">The definition of 'text-indent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`text-indent`

1

12

1

3

3.5

1

≤37

18

4

14

1

1.0

`each-line`

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

No

`hanging`

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

No

## See also

- [Learn to style HTML using CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS)
- Related CSS properties:
  - `text-justify`
  - `text-orientation`
  - `text-overflow`
  - `text-rendering`
  - `text-transform`
- [CSS Text Decoration](css_text_decoration) CSS module
- [CSS Text module](css_text)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent</a>
