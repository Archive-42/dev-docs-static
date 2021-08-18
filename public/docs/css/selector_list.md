# Selector list

The CSS **selector list** (`,`) selects all the matching nodes.

    /* Selects all matching elements */
    span,
    div {
      border: red 2px solid;
    }

To reduce the size of style sheets, one can group selectors in comma-separated lists.

## Syntax

    element, element, element { style properties }

## Examples

### Single Line Grouping

Grouping selectors in a single line using a comma-separated lists.

    h1, h2, h3, h4, h5, h6 { font-family: helvetica; }

### Multi Line Grouping

Grouping selectors in a multiple lines using a comma-separated lists.

    #main,
    .content,
    article {
      font-size: 1.1em;
    }

### Selector list invalidation

A downside to using selector lists is that the following aren't equivalent:

    h1 { font-family: sans-serif }
    h2:maybe-unsupported { font-family: sans-serif }
    h3 { font-family: sans-serif }

    h1, h2:maybe-unsupported, h3 { font-family: sans-serif }

This is because a single unsupported selector in a selector list invalidates the whole rule.

A way to remedy this us to use the [`:is()`](:is) or [`:where()`](:where) selectors, which accept a forgiving selector list. This will ignore invalid selectors in the list but accept those which are valid.

    h1 { font-family: sans-serif }
    h2:maybe-unsupported { font-family: sans-serif }
    h3 { font-family: sans-serif }

    :is(h1, h2:maybe-unsupported, h3) { font-family: sans-serif }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#grouping">Selectors Level 4<br />
<span class="small">The definition of 'Selector Lists' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Renamed to "selector list"</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#grouping">CSS Level 1<br />
<span class="small">The definition of 'grouping' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`Selector_list`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

## See also

- The [`:is()`](:is) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> and [`:where()`](:where) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> pseudo-classes, which accept a forgiving selector list.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list</a>
