# counter-reset

The `counter-reset` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property resets a [CSS counter](css_lists_and_counters/using_css_counters) to a given value.

**Note:** The counter's value can be increased or decreased using the [`counter-increment`](counter-increment) CSS property.

## Syntax

    /* Set "my-counter" to 0 */
    counter-reset: my-counter;

    /* Set "my-counter" to -1 */
    counter-reset: my-counter -1;

    /* Set "counter1" to 1, and "counter2" to 4 */
    counter-reset: counter1 1 counter2 4;

    /* Cancel any reset that could have been set in less specific rules */
    counter-reset: none;

    /* Global values */
    counter-reset: inherit;
    counter-reset: initial;
    counter-reset: unset;

The `counter-reset` property is specified as either one of the following:

- A `<custom-ident>` naming the counter, followed optionally by an `<integer>`. You may specify as many counters to reset as you want, with each name or name-number pair separated by a space.
- The keyword value `none`.

### Values

[`<custom-ident>`](custom-ident)  
The name of the counter to reset.

[`<integer>`](integer)  
The value to reset the counter to on each occurrence of the element. Defaults to `0` if not specified.

`none`  
No counter reset is to be performed. This can be used to override a `counter-reset` defined in a less specific rule.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ <custom-ident> <integer>? ]+ | none

## Examples

### Resetting named counters

    h1 {
      counter-reset: chapter section 1 page;
      /* Sets the chapter and page counters to 0,
         and the section counter to 1 */
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-lists-3/#counter-reset">CSS Lists Module Level 3<br />
<span class="small">The definition of 'counter-reset' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/generate.html#propdef-counter-reset">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'counter-reset' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`counter-reset`

2

12

1

8

9.2

3

≤37

18

25

10.1

1

1.0

## See also

- [Using CSS Counters](css_lists_and_counters/using_css_counters)
- [`counter-increment`](counter-increment)
- [`counter-set`](counter-set)
- [`@counter-style`](@counter-style)
- [`counter()`](<counter()>) and [`counters()`](<counters()>) functions
- [`content`](content) property

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/counter-reset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/counter-reset</a>
