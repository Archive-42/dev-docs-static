# hanging-punctuation

The `hanging-punctuation` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies whether a punctuation mark should hang at the start or end of a line of text. Hanging punctuation may be placed outside the line box.

    /* Keyword values */
    hanging-punctuation: none;
    hanging-punctuation: first;
    hanging-punctuation: last;
    hanging-punctuation: force-end;
    hanging-punctuation: allow-end;

    /* Two keywords */
    hanging-punctuation: first force-end;
    hanging-punctuation: first allow-end;
    hanging-punctuation: first last;
    hanging-punctuation: last force-end;
    hanging-punctuation: last allow-end;

    /* Three keywords */
    hanging-punctuation: first force-end last;
    hanging-punctuation: first allow-end last;

    /* Global values */
    hanging-punctuation: inherit;
    hanging-punctuation: initial;
    hanging-punctuation: unset;

## Syntax

The `hanging-punctuation` property may be specified with one, two, or three values.

- **One-value** syntax uses any one of the keyword values in the list below.
- **Two-value** syntax uses one of the following:
  - `first` together with any one of `last`, `allow-end`, or `force-end`
  - `last` together with any one of `first`, `allow-end`, or `force-end`
- **Three-value** syntax uses one of the following:
  - `first`, `allow-end`, and `last`
  - `first`, `force-end`, and `last`

### Values

`none`  
No character hangs.

`first`  
An opening bracket or quote at the start of the first formatted line of an element hangs.

`last`  
A closing bracket or quote at the end of the last formatted line of an element hangs.

`force-end`  
A stop or comma at the end of a line hangs.

`allow-end`  
A stop or comma at the end of a line hangs if it does not otherwise fit prior to justification.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | [ first || [ force-end | allow-end ] || last ]

## Examples

### Setting opening and closing quotes to hang

#### HTML

    <p>“Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur dignissim nunc mauris, et sollicitudin est scelerisque sed. Praesent laoreet tortor massa, sit amet vulputate nulla pharetra ut.”</p>

#### CSS

    p {
      hanging-punctuation: first last;
      margin: .5rem;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#hanging-punctuation-property">CSS Text Module Level 3<br />
<span class="small">The definition of 'hanging-punctuation' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`hanging-punctuation`

No

No

No

No

No

10

The `force-end` keyword is recognized but has no effect.

No

No

No

No

10

The `force-end` keyword is recognized but has no effect.

No

- [CSS Tricks: Hanging punctuation](https://css-tricks.com/almanac/properties/h/hanging-punctuation/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/hanging-punctuation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/hanging-punctuation</a>
