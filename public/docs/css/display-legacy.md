# &lt;display-legacy&gt;

CSS 2 used a single-keyword syntax for the `display` property, requiring separate keywords for block-level and inline-level variants of the same layout mode. This page details those values.

## Syntax

Valid `<display-legacy>` values:

`inline-block`  
The element generates a block element box that will be flowed with surrounding content as if it were a single inline box (behaving much like a replaced element would).

It is equivalent to `inline flow-root`.

`inline-table`  
The `inline-table` value does not have a direct mapping in HTML. It behaves like an HTML [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) element, but as an inline box, rather than a block-level box. Inside the table box is a block-level context.

It is equivalent to `inline table`.

`inline-flex`  
The element behaves like an inline element and lays out its content according to the flexbox model.

It is equivalent to `inline flex`.

`inline-grid`  
The element behaves like an inline element and lays out its content according to the grid model.

It is equivalent to `inline grid`.

## Examples

In the below example, we are creating an inline flex container with the legacy keyword inline-flex.

### HTML

    <div class="container">
      <div>Flex Item</div>
      <div>Flex Item</div>
    </div>

    Not a flex item

### CSS

    .container {
      display: inline-flex;
    }

### Result

In the new syntax the inline flex container would be created using two values, inline for the outer display type, and flex for the inner display type.

    .container {
      display: inline flex;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-display/#typedef-display-legacy">CSS Display Module Level 3<br />
<span class="small">The definition of 'display-legacy' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td></tr></tbody></table>

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

`display-legacy`

57

16

12

52

10

Internet Explorer implements an older version of the specification.

44

10.1

57

57

52

43

10.3

6.0

Samsung Internet added this earlier than the corresponding Chrome version would indicate.

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

`display-legacy`

29

21

12

20

Firefox 28 added multi-line flexbox support.

11

8

16

15

9

6.1

4.4

≤37

29

25

20

Firefox 28 added multi-line flexbox support.

16

14

9

6.1

2.0

1.5

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

`display-legacy`

1

12

3

8

7

1

≤37

18

4

14

1

1.0

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

`display-legacy`

1

12

1

8

6

Until Internet Explorer 8, `inline-block` is only for natural inline elements.

7

1

≤37

18

4

14

1

1.0

BCD tables only load in the browser

### Support of inline-table

BCD tables only load in the browser

### Support of inline-flex

BCD tables only load in the browser

### Support of inline-grid

BCD tables only load in the browser

## See also

- [`display`](display)
  - [`<display-outside>`](display-outside)
  - [`<display-inside>`](display-inside)
  - [`<display-listitem>`](display-listitem)
  - [`<display-internal>`](display-internal)
  - [`<display-box>`](display-box)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/display-legacy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/display-legacy</a>
