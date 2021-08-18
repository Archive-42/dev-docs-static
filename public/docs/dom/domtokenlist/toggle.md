DOMTokenList.toggle()
=====================

The `toggle()` method of the [`DOMTokenList`](../domtokenlist) interface removes a given `token` from the list and returns `false`. If `token` doesn't exist it's added and the function returns `true`.

Syntax
------

    tokenList.toggle(token [, force]);

### Parameters

`token`  
A [`DOMString`](../domstring) representing the token you want to toggle.

 `force` <span class="badge inline optional">Optional</span>   
If included, turns the toggle into a one way-only operation. If set to `false`, then `token` will *only* be removed, but not added. If set to `true`, then `token` will *only* be added, but not removed.

### Return value

`true` or `false`, indicating whether `token` is in the list after the call.

Examples
--------

In the following example we retrieve the list of classes set on a [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) element as a `DOMTokenList` using [`Element.classList`](../element/classlist). We then replace a token in the list, and write the list into the `<span>`'s [`Node.textContent`](../node/textcontent).

First, the HTML:

    <span class="a b">classList is 'a b'</span>

Now the JavaScript:

    let span = document.querySelector("span");
    let classes = span.classList;

    span.addEventListener('click', function() {
      let result = classes.toggle("c");

      if (result) {
        span.textContent = `'c' added; classList is now "${classes}".`;
      } else {
        span.textContent = `'c' removed; classList is now "${classes}".`;
      }
    })

The output looks like this:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-domtokenlist-toggle">DOM<br />
<span class="small">The definition of 'toggle()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`toggle`

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

`force_argument`

24

≤18

24

No

≤15

6.1

≤37

25

24

≤14

6.1

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/toggle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/toggle</a>
