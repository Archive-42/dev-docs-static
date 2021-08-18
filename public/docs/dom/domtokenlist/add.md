# DOMTokenList.add()

The `add()` method of the [`DOMTokenList`](../domtokenlist) interface adds the given _token_ to the list.

## Syntax

    tokenList.add(token1[, token2[, ...tokenN]]);

### Parameters

`tokenN`  
A [`DOMString`](../domstring) representing the token (or tokens) to add to the `tokenList`.

### Return value

`undefined`

## Examples

In the following example we retrieve the list of classes set on a [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) element as a `DOMTokenList` using [`Element.classList`](../element/classlist). We then add a new token to the list, and write the list into the `<span>`'s [`Node.textContent`](../node/textcontent).

First, the HTML:

    <span class="a b c"></span>

Now the JavaScript:

    let span = document.querySelector("span");
    let classes = span.classList;
    classes.add("d");
    span.textContent = classes;

The output looks like this:

You can add multiple tokens as well:

    span.classList.add("d", "e", "f");

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-domtokenlist-add">DOM<br />
<span class="small">The definition of 'add()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`add`

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

`add_multiple_arguments`

24

12

26

No

15

7

≤37

25

26

14

7

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/add" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/add</a>
