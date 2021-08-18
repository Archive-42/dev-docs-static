# initial-letter

The `initial-letter` CSS property sets styling for dropped, raised, and sunken initial letters.

    /* Keyword values */
    initial-letter: normal;

    /* Numeric values */
    initial-letter: 1.5;    /* Initial letter occupies 1.5 lines */
    initial-letter: 3.0;    /* Initial letter occupies 3 lines */
    initial-letter: 3.0 2;  /* Initial letter occupies 3 lines and
                               sinks 2 lines */

    /* Global values */
    initial-letter: inherit;
    initial-letter: initial;
    initial-letter: unset;

## Syntax

The keyword value `normal`, or a `<number>` optionally followed by an `<integer>`.

### Values

`normal`  
No special initial-letter effect. Text behaves as normal.

`<number>`  
Defines the size of the initial letter, in terms of how many lines it occupies. Negative values are not allowed.

`<integer>`  
Defines the number of lines the initial letter should sink when the size of it is given. Values must be greater than zero. If omitted, it duplicates the size value, floored to the nearest positive whole number.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td><a href="::first-letter"><code>::first-letter</code></a> pseudo-elements and inline-level first child of a block container</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | [ <number> <integer>? ]

## Examples

### Setting initial letter size

#### HTML

    <p class="normal">Initial letter is normal</p>
    <p class="onefive">Initial letter occupies 1.5 lines</p>
    <p class="three">Initial letter occupies 3 lines</p>

#### CSS

    .normal {
      -webkit-initial-letter: normal;
      initial-letter: normal;
    }

    .onefive {
      -webkit-initial-letter: 1.5;
      initial-letter: 1.5;
    }

    .three {
      -webkit-initial-letter: 3.0;
      initial-letter: 3.0;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-inline/#sizing-drop-initials">CSS Inline Layout<br />
<span class="small">The definition of 'initial-letter' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`initial-letter`

No

No

No

See [bug 1223880](https://bugzil.la/1223880)

No

No

9

No

No

No

See [bug 1223880](https://bugzil.la/1223880)

No

9

No

- [`initial-letter-align`](initial-letter-align)
- [Drop caps in CSS](https://www.oddbird.net/2017/01/03/initial-letter/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/initial-letter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/initial-letter</a>
