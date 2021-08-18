# text-align-last

The `text-align-last` CSS property sets how the last line of a block or a line, right before a forced line break, is aligned.

## Syntax

    /* Keyword values */
    text-align-last: auto;
    text-align-last: start;
    text-align-last: end;
    text-align-last: left;
    text-align-last: right;
    text-align-last: center;
    text-align-last: justify;

    /* Global values */
    text-align-last: inherit;
    text-align-last: initial;
    text-align-last: unset;

### Values

`auto`  
The affected line is aligned per the value of [`text-align`](text-align), unless [`text-align`](text-align) is `justify`, in which case the effect is the same as setting `text-align-last` to `start`.

`start`  
The same as `left` if direction is left-to-right and `right` if direction is right-to-left.

`end`  
The same as `right` if direction is left-to-right and `left` if direction is right-to-left.

`left`  
The inline contents are aligned to the left edge of the line box.

`right`  
The inline contents are aligned to the right edge of the line box.

`center`  
The inline contents are centered within the line box.

`justify`  
The text is justified. Text should line up their left and right edges to the left and right content edges of the paragraph.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>block containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | start | end | left | right | center | justify

## Examples

### Justifying the last line

#### CSS

    p {
      font-size: 1.4em;
      text-align: justify;
      text-align-last: center;
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#text-align-last-property">CSS Text Module Level 3<br />
<span class="small">The definition of 'text-align-last' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`text-align-last`

47

12

49

12-53

5.5

\["IE only supports `text-align-last` when `text-align` is set to `justify`.", "The `start` and `end` values are not supported."\]

34

No

See WebKit [bug 76173](https://webkit.org/b/76173).

47

47

49

14-53

34

No

See WebKit [bug 76173](https://webkit.org/b/76173).

5.0

## See also

- [`text-align`](text-align)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-align-last" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-align-last</a>
