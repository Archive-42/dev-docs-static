# :autofill

The `:autofill` CSS [pseudo-class](pseudo-classes) matches when an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element has its value autofilled by the browser. The class stops matching if the user edits the field.

**Note:** The user agent style sheets of many browsers use `!important` in their `:-webkit-autofill` style declarations, making them non-overrideable by webpages without resorting to JavaScript hacks. For example Chrome has the following in its internal stylesheet:

    background-color: rgb(232, 240, 254) !important;
    background-image: none !important;
    color: -internal-light-dark(black, white) !important;

This means that you cannot set the [`background-color`](background-color), [`background-image`](background-image), or [`color`](color) in your own rules.

## Syntax

    :autofill

## Examples

The following example demonstrates the use of the `:autofill` pseudo-class to change the border of a text field that has been autocompleted by the browser. For the best browser compatibility use both `:-webkit-autofill` and `:autofill`.

    input {
      border: 3px solid grey;
      border-radius: 3px;
    }

    input:-webkit-autofill {
      border: 3px solid blue;
    }
    input:autofill {
      border: 3px solid blue;
    }

    <form method="post" action="">
      <label for="email">Email</label> <input type="email" name="email" id="email" autocomplete="email">
    </form>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#selector-autofill">HTML Living Standard<br />
<span class="small">The definition of ':auto-fill, :-webkit-autofill' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`:autofill`

1

79

86

86

No

15

3

1

18

86

86

14

1

1.0

## See also

- [Chromium issue 46543: Auto-filled input text box yellow background highlight cannot be turned off!](https://code.google.com/p/chromium/issues/detail?id=46543)
- [WebKit bug 66032: Allow site authors to override autofilled fields' colors.](https://bugs.webkit.org/show_bug.cgi?id=66032)
- [Mozilla bug 740979: implement `:-moz-autofill` pseudo-class on input elements with an autofilled value](https://bugzilla.mozilla.org/show_bug.cgi?id=740979)
- [new css4-ui features - more selectors](https://wiki.csswg.org/spec/css4-ui#more-selectors)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:autofill" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:autofill</a>
