# counter-set

The `counter-set` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets a [CSS counter](css_lists_and_counters/using_css_counters) to a given value. It manipulates the value of existing counters, and will only create new counters if there isn't already a counter of the given name on the element.

**Note:** The counter's value can be incremented or decremented using the [`counter-increment`](counter-increment) CSS property.

## Syntax

    /* Set "my-counter" to 0 */
    counter-set: my-counter;

    /* Set "my-counter" to -1 */
    counter-set: my-counter -1;

    /* Set "counter1" to 1, and "counter2" to 4 */
    counter-set: counter1 1 counter2 4;

    /* Cancel any counter that could have been set in less specific rules */
    counter-set: none;

    /* Global values */
    counter-set: inherit;
    counter-set: initial;
    counter-set: unset;

The `counter-set` property is specified as either one of the following:

- A `<custom-ident>` naming the counter, followed optionally by an `<integer>`. You may specify as many counters to reset as you want, with each name or name-number pair separated by a space.
- The keyword value `none`.

### Values

[`<custom-ident>`](custom-ident)  
The name of the counter to set.

[`<integer>`](integer)  
The value to set the counter to on each occurrence of the element. Defaults to `0` if not specified. If there isn't currently a counter of the given name on the element, the element will create a new counter of the given name with a starting value of 0 (though it may then immediately set or increment that value to something different).

`none`  
No counter set is to be performed. This can be used to override a `counter-set` defined in a less specific rule.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ <custom-ident> <integer>? ]+ | none

## Examples

### Setting named counters

    h1 {
      counter-set: chapter section 1 page;
      /* Sets the chapter and page counters to 0,
         and the section counter to 1 */
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-lists-3/#propdef-counter-set">CSS Lists Module Level 3<br />
<span class="small">The definition of 'counter-set' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`counter-set`

85

85

68

No

71

No

85

85

68

60

No

No

## See also

- [Using CSS Counters](css_lists_and_counters/using_css_counters)
- [`counter-increment`](counter-increment)
- [`counter-reset`](counter-reset)
- [`@counter-style`](@counter-style)
- [`counter()`](<counter()>) and [`counters()`](<counters()>) functions
- [`content`](content) property

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/counter-set" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/counter-set</a>
