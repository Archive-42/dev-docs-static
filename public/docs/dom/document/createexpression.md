# Document.createExpression()

This method compiles an [`XPathExpression`](../xpathexpression) which can then be used for (repeated) evaluations.

## Syntax

    xpathExpr = document.createExpression(xpathText, namespaceURLMapper);

### Parameters

- xpathText is a string which is the XPath expression to be compiled.
- namespaceURLMapper is a function which maps a namespace prefix to a namespace URL (or null if none needed).

**[Firefox 3 note](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/3)**

Prior to Firefox 3, you could call this method on documents other than the one you planned to run the XPath against. Under Firefox 3, you must call it on the same document.

### Return value

[`XPathExpression`](../xpathexpression)

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

`createExpression`

1

12

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

## See also

- [`Document.evaluate()`](evaluate)
- [`XPathExpression`](../xpathexpression)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createExpression" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createExpression</a>
