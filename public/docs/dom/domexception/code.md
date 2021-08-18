# DOMException.code

The `code` read-only property of the [`DOMException`](../domexception) interface returns a `short` that contains one of the [error code constants](../domexception#error_names), or `0` if none match. This field is used for historical reasons. New DOM exceptions don't use this anymore: they put this info in the [`DOMException.name`](name) attribute.

## Syntax

    var domExceptionCode = domExceptionInstance.code;

### Value

A short number.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://heycam.github.io/webidl/#dom-domexception-code">Web IDL<br />
<span class="small">The definition of 'code' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`code`

1

12

1

10

≤15

1

1

18

4

≤14

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMException/code" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMException/code</a>
