# symbols()

The `symbols()` CSS function lets you define counter styles inline, directly as the value of a property such as [`list-style`](list-style). Unlike [`@counter-style`](@counter-style), `symbols()` is _anonymous_ (i.e., it can only be used once). Although less powerful, it is shorter and easier to write than [`@counter-style`](@counter-style).

## Syntax

    symbols() = symbols( <symbols-type>? [ <string> | <image> ]+ );

`<symbols-type>` can be one of the following:

- `cyclic`: The system cycles through the given values in the order of their definition, and returns to the start when it reaches the end.
- `numeric`: The system interprets the given values as the successive units of a place-value numbering system.
- `alphabetic`: The system interprets the given values as the digits of an alphabetic numbering system, like a place-value numbering system but without `0`.
- `symbolic`: The system cycles through the values, printing them an additional time at each cycle (one time for the first cycle, two times for the second, etc.).
- `fixed`: The system cycles through the given values once, then falls back to Arabic numerals.

## Examples

### HTML

    <ol>
      <li>One</li>
      <li>Two</li>
      <li>Three</li>
      <li>Four</li>
      <li>Five</li>
    </ol>

### CSS

    ol {
      list-style: symbols(cyclic "*" "†" "‡");
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-counter-styles-3/#symbols-function">CSS Counter Styles Level 3<br />
<span class="small">The definition of 'symbols()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`symbols()`

No

No

35

No

No

No

No

No

35

No

No

No

## See also

- [`@counter-style`](@counter-style)
- [`list-style-type`](list-style-type) and the corresponding shorthand [`list-style`](list-style).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/symbols()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/symbols()</a>
