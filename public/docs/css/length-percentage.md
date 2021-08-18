# &lt;length-percentage&gt;

The `<length-percentage>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a value that can be either a [`<length>`](length) or a [`<percentage>`](percentage).

## Syntax

Refer to the documentation for [`<length>`](length) and [`<percentage>`](percentage) for details of the individual syntaxes allowed by this type.

## Examples

### length-percentage examples

The following simple example demonstrates several properties that use `<length-percentage>` values.

#### HTML

    <p>You can use percentages and lengths in so many places.</p>

#### CSS

    p {
      /* length-percentage examples */
      width: 75%;
      height: 200px;
      margin: 3rem;
      padding: 1%;
      border-radius: 10px 10%;
      font-size: 250%;
      line-height: 1.5em;

      /* length examples */
      text-shadow: 1px 1px 1px red;
      border: 5px solid red;
      letter-spacing: 3px;

      /* percentage example */
      text-size-adjust: 20%;
    }

#### Result

### Use in calc()

Where a `<length-percentage>` is specified as an allowable type, this means that the percentage resolves to a length and therefore can be used in a [`calc()`](<calc()>) expression. Therefore, all of the following values are acceptable for [`width`](width):

    width: 200px;
    width: 20%;
    width: calc(100% - 200px);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#mixed-percentages">CSS Values and Units Module Level 4<br />
<span class="small">The definition of '&lt;length-percentage&gt;' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#mixed-percentages">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '&lt;length-percentage&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines <code>&lt;length-percentage&gt;</code>. Adds <code>calc()</code></td></tr></tbody></table>

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

`length-percentage`

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

`Q`

63

79

49

No

50

No

63

63

49

46

No

8.0

`cap`

No

No

No

No

No

No

No

No

No

No

No

No

`ch`

27

12

1

\["From Firefox 1 to Firefox 3, `ch` was the width of the _M_ character.", "From Firefox 1 to Firefox 3, `ch` did not work with [`border-width`](https://developer.mozilla.org/docs/Web/CSS/border-width) and [`outline-width`](https://developer.mozilla.org/docs/Web/CSS/outline-width) CSS properties."\]

9

20

7

≤37

27

4

14

7

1.5

`ex`

1

12

1

4

3.5

1

1

18

4

10.1

1

1.0

`ic`

No

No

No

See [bug 1531223](https://bugzil.la/1531223)

No

No

No

See [bug 195176](https://webkit.org/b/195176)

No

No

No

No

No

No

`lh`

No

See [bug 937104](https://crbug.com/937104)

No

No

See [bug 1310170](https://bugzil.la/1310170)

No

No

No

No

No

No

No

No

No

`mozmm`

No

No

4-59

No

No

No

No

No

4-59

No

No

No

`rem`

4

12

3.6

9

11.6

5

2

18

4

12

4

1.0

`rlh`

No

See [bug 937104](https://crbug.com/937104)

No

No

See [bug 1310170](https://bugzil.la/1310170)

No

No

No

No

No

No

No

No

No

`vb`

No

No

No

See [bug 1287034](https://bugzil.la/1287034)

No

No

No

See [bug 159801](https://webkit.org/b/159801)

No

No

No

No

No

No

`vh`

20

12

19

9

20

6

≤37

25

19

14

6

1.5

`vi`

No

No

No

See [bug 1287034](https://bugzil.la/1287034)

No

No

No

See [bug 159801](https://webkit.org/b/159801)

No

No

No

No

No

No

`vmax`

26

16

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

No

15

6.1

1.5

26

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

14

6.1

1.5

`vmin`

26

12

12

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

10

9

15

6.1

≤37

26

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

14

6.1

1.5

`vw`

20

12

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

9

20

6

≤37

25

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

14

6

1.5

## See also

## See also

- [`<percentage>`](percentage)
- [`<length>`](length)
- [CSS Values and Units](css_values_and_units)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage</a>
