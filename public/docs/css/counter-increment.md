# counter-increment

The `counter-increment` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property increases or decreases the value of a [CSS counter](css_lists_and_counters/using_css_counters) by a given value.

**Note:** The counter's value can be reset to an arbitrary number using the [`counter-reset`](counter-reset) CSS property.

## Syntax

    /* Increment "my-counter" by 1 */
    counter-increment: my-counter;

    /* Decrement "my-counter" by 1 */
    counter-increment: my-counter -1;

    /* Increment "counter1" by 1, and decrement "counter2" by 4 */
    counter-increment: counter1 counter2 -4;

    /* Do not increment/decrement anything: used to override less specific rules */
    counter-increment: none;

    /* Global values */
    counter-increment: inherit;
    counter-increment: initial;
    counter-increment: unset;

The `counter-increment` property is specified as either one of the following:

- A `<custom-ident>` naming the counter, followed optionally by an `<integer>`. You may specify as many counters to increment as you want, with each name or name-number pair separated by a space.
- The keyword value `none`.

### Values

[`<custom-ident>`](custom-ident)  
The name of the counter to increment.

[`<integer>`](integer)  
The value to add to the counter. Defaults to `1` if not specified.

`none`  
No counter must be incremented. This is used as the default value, or to cancel an increment in more specific rules.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ <custom-ident> <integer>? ]+ | none

## Examples

### Incrementing named counters

    h1 {
      counter-increment: chapter section 2 page;
      /* Increases the value of the chapter and page counters by 1,
         and the section counter by 2 */
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-lists-3/#propdef-counter-increment">CSS Lists Module Level 3<br />
<span class="small">The definition of 'counter-increment' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/generate.html#propdef-counter-increment">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'counter-increment' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`counter-increment`

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
- [`counter-reset`](counter-reset)
- [`counter-set`](counter-set)
- [`@counter-style`](@counter-style)
- The [`counter()`](<counter()>) and [`counters()`](<counters()>) functions

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/counter-increment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/counter-increment</a>
