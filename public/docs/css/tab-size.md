# tab-size

The `tab-size` CSS property is used to customize the width of tab characters (U+0009).

## Syntax

    /* <integer> values */
    tab-size: 4;
    tab-size: 0;

    /* <length> values */
    tab-size: 10px;
    tab-size: 2em;

    /* Global values */
    tab-size: inherit;
    tab-size: initial;
    tab-size: unset;

### Values

[`<integer>`](integer)  
A multiple of the advance width of the space character (U+0020) to be used as the width of tabs. Must be nonnegative.

[`<length>`](length)  
The width of tabs. Must be nonnegative.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>8</code></td></tr><tr class="even"><td>Applies to</td><td>block containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>the specified integer or an absolute length</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <integer> | <length>

## Examples

### Expanding by character count

    pre {
      tab-size: 4; /* Set tab size to 4 characters wide */
    }

### Collapse tabs

    pre {
      tab-size: 0; /* Remove indentation */
    }

### Comparing to the default size

This example compares a default tab size with a custom tab size. Note that [`white-space`](white-space) is set to `pre` to prevent the tabs from collapsing.

#### HTML

    <p>no tab</p>
    <p>&#0009;default tab size of 8 characters wide</p>
    <p class="custom">&#0009;custom tab size of 3 characters wide</p>
    <p>&nbsp;&nbsp;&nbsp;3 spaces, equivalent to the custom tab size</p>

#### CSS

    p {
      white-space: pre;
    }

    .custom {
      tab-size: 3;
      -moz-tab-size: 3;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#tab-size-property">CSS Text Module Level 3<br />
<span class="small">The definition of 'tab-size' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`tab-size`

21

This property is not yet animatable.

79

This property is not yet animatable.

4

\["See [bug 737785](https://bugzil.la/737785) for the status of unprefixing this property.", "Before Firefox 53, this property was not animatable."\]

No

15

10.5-15

6.1

4.4

25

This property is not yet animatable.

4

\["See [bug 737785](https://bugzil.la/737785) for the status of unprefixing this property.", "Before Firefox 53, this property was not animatable."\]

14

11-14

7

1.5

This property is not yet animatable.

`length`

42

79

53

No

29

No

56

42

53

29

No

4.0

## See also

- [Controlling size of a tab character (U+0009)](https://lists.w3.org/Archives/Public/www-style/2008Dec/0009.html), an email by Anne van Kesteren to the CSSWG.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/tab-size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/tab-size</a>
