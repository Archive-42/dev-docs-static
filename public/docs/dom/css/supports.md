# CSS.supports()

The `CSS.supports()` method returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating if the browser supports a given CSS feature, or not.

## Syntax

    CSS.supports(propertyName, value);
    CSS.supports(supportCondition);

### Parameters

There are two distinct sets of parameters. The first one allows to test the support of a pair _property-value_:

`propertyName`  
A [`DOMString`](../domstring) containing the name of the CSS property to check.

`value`  
A [`DOMString`](../domstring) containing the value of the CSS property to check.

The second syntax takes one parameter matching the condition of [`@supports`](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports):

`supportCondition`  
A [`DOMString`](../domstring) containing the condition to check.

### Return value

`true` if the browser supports the rule, otherwise `false`.

## Examples

    result = CSS.supports("text-decoration-style", "blink");
    result = CSS.supports("display: flex");
    result = CSS.supports("(--foo: red)");

    result = CSS.supports(`(transform-style: preserve) or (-moz-transform-style: preserve) or
                           (-o-transform-style: preserve) or (-webkit-transform-style: preserve)`);

    // result is true or false

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-conditional-3/#dom-css-supports">CSS Conditional Rules Module Level 3<br />
<span class="small">The definition of 'CSS: supports()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`supports`

61

28

Version 60 or older didn't support parentheses-less one-argument version.

12

Edge doesn't support parentheses-less one-argument version.

55

22

Version 54 or older didn't support parentheses-less one-argument version.

No

12.1

10

61

37

Version 60 or older didn't support parentheses-less one-argument version.

61

28

Version 60 or older didn't support parentheses-less one-argument version.

55

22

Version 54 or older didn't support parentheses-less one-argument version.

12.1

Yes

8.0

1.5

Samsung Internet 8.0 or older didn't support parentheses-less one-argument version.

## See also

- The [`@supports`](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports) at-rule that allows for the same functionality but in a declarative way.
- The [`CSSSupportsRule`](../csssupportsrule) CSSOM class allowing to manipulate [`@supports`](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports) at-rules.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS/supports" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS/supports</a>
