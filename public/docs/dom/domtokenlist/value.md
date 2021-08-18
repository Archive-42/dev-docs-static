# DOMTokenList.value

The `value` property of the [`DOMTokenList`](../domtokenlist) interface is a stringifier that returns the value of the list as a [`DOMString`](../domstring), or clears and sets the list to the given value.

## Syntax

    tokenList.value;

### Value

A [`DOMString`](../domstring)

## Examples

In the following example we retrieve the list of classes set on a [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) element as a `DOMTokenList` using [`Element.classList`](../element/classlist), then write the value of the list to the `<span>`'s [`Node.textContent`](../node/textcontent).

First, the HTML:

    <span class="a b c"></span>

Now the JavaScript:

    let span = document.querySelector("span");
    let classes = span.classList;
    span.textContent = classes.value;

The output looks like this:

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-domtokenlist-value">DOM<br />
<span class="small">The definition of 'value' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`value`

50

Before Chrome 50, this property was part of the deprecated child `DOMSettableTokenList` interface.

17

47

No

37

Before Opera 37, this property was part of the deprecated child `DOMSettableTokenList` interface.

10

50

Before Chrome 50, this property was part of the deprecated child `DOMSettableTokenList` interface.

50

Before Chrome 50, this property was part of the deprecated child `DOMSettableTokenList` interface.

47

37

Before Opera 37, this property was part of the deprecated child `DOMSettableTokenList` interface.

10

5.0

Before Samsung Internet 5.0, this property was part of the deprecated child `DOMSettableTokenList` interface.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/value</a>
