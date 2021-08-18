# DOMTokenList.contains()

The `contains()` method of the [`DOMTokenList`](../domtokenlist) interface returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) — `true` if the underlying list contains the given `token`, otherwise `false`.

## Syntax

    tokenList.contains(token);

### Parameters

`token`  
A [`DOMString`](../domstring) representing the token you want to check for the existence of in the list.

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), which is `true` if the calling list contains `token`, otherwise `false`.

## Examples

In the following example we retrieve the list of classes set on a [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) element as a `DOMTokenList` using [`Element.classList`](../element/classlist). We then test for the existence of `"c"` in the list, and write the result into the `<span>`'s [`Node.textContent`](../node/textcontent).

First, the HTML:

    <span class="a b c"></span>

Now the JavaScript:

    let span = document.querySelector("span");
    let classes = span.classList;
    let result = classes.contains("c");
    if (result) {
      span.textContent = "The classList contains 'c'";
    } else {
       span.textContent = "The classList does not contain 'c'";
    }

The output looks like this:

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-domtokenlist-contains">DOM<br />
<span class="small">The definition of 'contains()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`contains`

8

12

3.6

10

Yes

5.1

3

18

4

Yes

5.1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/contains" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/contains</a>
