# DOMException()

The `DOMException()` constructor returns a `DOMException` object with a specified message and name.

## Syntax

    var domException = new DOMException();
    var domException = new DOMException(message);
    var domException = new DOMException(message, name);

### Parameters

`message` <span class="badge inline optional">Optional</span>  
A description of the exception. If not present, the empty string `''` is used.

`name` <span class="badge inline optional">Optional</span>  
Returns a [`DOMString`](../domstring) that contains one of the strings associated with an [error constant](web/api/domexception#Error_constants).

### Return value

**[`DOMException`](../domexception)**  
A newly created [`DOMException`](../domexception) object.

## Example

TBD

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://heycam.github.io/webidl/#dom-domexception-domexception">Web IDL<br />
<span class="small">The definition of 'DOMException()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds the constructor for the <code>DOMException</code> class.</td></tr></tbody></table>

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

`DOMException`

46

79

37

No

33

10.1

46

46

37

33

10.3

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMException/DOMException" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMException/DOMException</a>
