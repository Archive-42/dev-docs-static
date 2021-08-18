# :nth-last-child()

The `:nth-last-child()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) matches elements based on their position among a group of siblings, counting from the end.

    /* Selects every fourth element
       among any group of siblings,
       counting backwards from the last one */
    :nth-last-child(4n) {
      color: lime;
    }

**Note:** This pseudo-class is essentially the same as [`:nth-child`](:nth-child), except it counts items backwards from the _end_, not forwards from the beginning.

## Syntax

The `nth-last-child` pseudo-class is specified with a single argument, which represents the pattern for matching elements, counting from the end.

### Keyword values

`odd`  
Represents elements whose numeric position in a series of siblings is odd: 1, 3, 5, etc., counting from the end.

`even`  
Represents elements whose numeric position in a series of siblings is even: 2, 4, 6, etc., counting from the end.

### Functional notation

`<An+B>`  
Represents elements whose numeric position in a series of siblings matches the pattern `An+B`, for every positive integer or zero value of `n`. The index of the first element, counting from the end, is `1`. The values `A` and `B` must both be [`<integer>`](integer)s.

### Formal syntax

    :nth-last-child( <nth> [ of <complex-selector-list> ]? )where
    <nth> = <an-plus-b> | even | odd
    <complex-selector-list> = <complex-selector>#where
    <complex-selector> = <compound-selector> [ <combinator>? <compound-selector> ]*where
    <compound-selector> = [ <type-selector>? <subclass-selector>* [ <pseudo-element-selector> <pseudo-class-selector>* ]* ]!
    <combinator> = '>' | '+' | '~' | [ '||' ]where
    <type-selector> = <wq-name> | <ns-prefix>? '*'
    <subclass-selector> = <id-selector> | <class-selector> | <attribute-selector> | <pseudo-class-selector>
    <pseudo-element-selector> = ':' <pseudo-class-selector>
    <pseudo-class-selector> = ':' <ident-token> | ':' <function-token> <any-value> ')'where
    <wq-name> = <ns-prefix>? <ident-token>
    <ns-prefix> = [ <ident-token> | '*' ]?  |
    <id-selector> = <hash-token>
    <class-selector> = '.' <ident-token>
    <attribute-selector> = '[' <wq-name> ']' | '[' <wq-name> <attr-matcher> [ <string-token> | <ident-token> ] <attr-modifier>? ']'
    where
    <attr-matcher> = [ '~' |  |  | '^' | '$' | '*' ]? '='
    <attr-modifier> = i | s

## Examples

### Example selectors

`tr:nth-last-child(odd)` or `tr:nth-last-child(2n+1)`  
Represents the odd rows of an HTML table: 1, 3, 5, etc., counting from the end.

`tr:nth-last-child(even)` or `tr:nth-last-child(2n)`  
Represents the even rows of an HTML table: 2, 4, 6, etc., counting from the end.

`:nth-last-child(7)`  
Represents the seventh element, counting from the end.

`:nth-last-child(5n)`  
Represents elements 5, 10, 15, etc., counting from the end.

`:nth-last-child(3n+4)`  
Represents elements 4, 7, 10, 13, etc., counting from the end.

`:nth-last-child(-n+3)`  
Represents the last three elements among a group of siblings.

`p:nth-last-child(n)` or `p:nth-last-child(n+1)`  
Represents every `<p>` element among a group of siblings. This is the same as a simple `p` selector. (Since `n` starts at zero, while the last element begins at one, `n` and `n+1` will both select the same elements.)

`p:nth-last-child(1)` or `p:nth-last-child(0n+1)`  
Represents every `<p>` that is the first element among a group of siblings, counting from the end. This is the same as the [`:last-child`](:last-child) selector.

### Table example

#### HTML

    <table>
      <tbody>
        <tr>
          <td>First line</td>
        </tr>
        <tr>
          <td>Second line</td>
        </tr>
        <tr>
          <td>Third line</td>
        </tr>
        <tr>
          <td>Fourth line</td>
        </tr>
        <tr>
          <td>Fifth line</td>
        </tr>
      </tbody>
    </table>

#### CSS

    table {
      border: 1px solid blue;
    }

    /* Selects the last three elements */
    tr:nth-last-child(-n+3) {
      background-color: pink;
    }

    /* Selects every element starting from the second to last item */
    tr:nth-last-child(n+2) {
      color: blue;
    }

    /* Select only the last second element */
    tr:nth-last-child(2) {
      font-weight: 600;
    }

#### Result

### Quantity query

A _quantity query_ styles elements depending on how many of them there are. In this example, list items turn red when there are at least three of them in a given list. This is accomplished by combining the capabilities of the `nth-last-child` pseudo-class and the [general sibling combinator](general_sibling_combinator).

#### HTML

    <h4>A list of four items (styled):</h4>
    <ol>
      <li>One</li>
      <li>Two</li>
      <li>Three</li>
      <li>Four</li>
    </ol>

    <h4>A list of two items (unstyled):</h4>
    <ol>
      <li>One</li>
      <li>Two</li>
    </ol>

#### CSS

    /* If there are at least three list items,
       style them all */
    li:nth-last-child(n+3),
    li:nth-last-child(n+3) ~ li {
      color: red;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#nth-last-child-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':nth-last-child' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Matching elements are not required to have a parent.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#nth-last-child-pseudo">Selectors Level 3<br />
<span class="small">The definition of ':nth-last-child' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:nth-last-child`

4

12

3.5

9

9

3.2

≤37

18

4

10.1

3.2

1.0

`no_parent_required`

57

79

52

No

44

No

57

57

52

43

No

7.0

`of_syntax`

No

See [bug 304163](https://crbug.com/304163).

No

See [bug 304163](https://crbug.com/304163).

No

See [bug 854148](https://bugzil.la/854148).

No

No

9

No

No

No

See [bug 854148](https://bugzil.la/854148).

No

9

No

## See also

- [`:nth-child`](:nth-child), [`:nth-last-of-type`](:nth-last-of-type)
- [Quantity Queries for CSS](https://alistapart.com/article/quantity-queries-for-css)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-child" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-child</a>
