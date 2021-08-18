# DOMTokenList.item()

The `item()` method of the [`DOMTokenList`](../domtokenlist) interface returns an item in the list by its index.

## Syntax

    tokenList.item(index)

### Parameters

`index`  
A 32-bit unsigned integer ([`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)) representing the index of the item you want to return.

### Return value

A [`DOMString`](../domstring) representing the returned item. It returns `null` if the number is greater than or equal to the `length` of the list.

## Examples

In the following example we retrieve the list of classes set on a [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) element as a `DOMTokenList` using [`Element.classList`](../element/classlist). We then retrieve the last item in the list using `item(tokenList.length - 1)`, and write it into the `<span>`'s [`Node.textContent`](../node/textcontent).

First, the HTML:

    <span class="a b c"></span>

Now the JavaScript:

    let span = document.querySelector("span");
    let classes = span.classList;
    let item = classes.item(classes.length-1);
    span.textContent = item;

The output looks like this:

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-domtokenlist-item">DOM<br />
<span class="small">The definition of 'item()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`item`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/item" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/item</a>
