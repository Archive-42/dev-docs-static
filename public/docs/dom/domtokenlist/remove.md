DOMTokenList.remove()
=====================

The `remove()` method of the [`DOMTokenList`](../domtokenlist) interface removes the specified *tokens* from the list.

Syntax
------

    tokenList.remove(token1[, token2[, ...tokenN]]);

### Parameters

`tokenN`  
A [`DOMString`](../domstring) representing the token you want to remove from the list. If the string is not in the list, no error is thrown, and nothing happens.

### Return value

`undefined`

Examples
--------

In the following example we retrieve the list of classes set on a [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) element as a `DOMTokenList` using [`Element.classList`](../element/classlist). We then remove a token from the list, and write the list into the `<span>`'s [`Node.textContent`](../node/textcontent).

First, the HTML:

    <div id="ab" class="a b c"></div>
    <div id="a" class="a b c"></div>

Now the JavaScript:

    let span = document.getElementById("ab");
    let classes = span.classList;
    classes.remove("c");
    span.textContent = classes;

To remove multiple classes at once, you can supply multiple tokens. The order you supply the tokens doesn't have to match the order they appear in the list:

    let span2 = document.getElementById("a")
    let classes2 = span2.classList;

    classes2.remove("c", "b");
    span2.textContent = classes2;

The output looks like this:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-domtokenlist-remove">DOM<br />
<span class="small">The definition of 'remove()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

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

`remove`

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

`remove_multiple_arguments`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/remove" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/remove</a>
