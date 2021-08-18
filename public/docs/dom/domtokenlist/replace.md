DOMTokenList.replace()
======================

The `replace()` method of the [`DOMTokenList`](../domtokenlist) interface replaces an existing token with a new token. If the first token doesn't exist, `replace()` returns `false` immediately, without adding the new token to the token list.

Syntax
------

    tokenList.replace(oldToken, newToken);

### Parameters

`oldToken`  
A [`DOMString`](../domstring) representing the token you want to replace.

`newToken`  
A [`DOMString`](../domstring) representing the token you want to replace `oldToken` with.

### Return value

A boolean value, which is `true` if `oldToken` was successfully replaced, or `false` if not.

**Note**: In older browsers, `replace()` returns void.

Examples
--------

In the following example we retrieve the list of classes set on a [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) element as a `DOMTokenList` using [`Element.classList`](../element/classlist). We then replace a token in the list, and write the list into the `<span>`'s [`Node.textContent`](../node/textcontent).

First, the HTML:

    <span class="a b c"></span>

Now the JavaScript:

    let span = document.querySelector("span");
    let classes = span.classList;

    let result = classes.replace("c", "z");
    console.log(result);

    if (result) {
      span.textContent = classes;
    } else {
      span.textContent = 'token not replaced successfully';
    }

The output looks like this:

Polyfill
--------

The following polyfill will add the replace method to the `DOMTokenList` class. The following code will only work with **IE10-11**. To use with earlier versions of IE, refer to the polyfill at [`element.classList#Polyfill`](../element/classlist#polyfill)

    DOMTokenList.prototype.replace = function (a, b) {
        if (this.contains(a)) {
            this.add(b);
            this.remove(a);
            return true;
        }
        return false;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-domtokenlist-replace">DOM<br />
<span class="small">The definition of 'replace()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`replace`

61

17

49

No

48

10.1

61

61

49

45

10.3

8.0

`boolean_value`

67

18

61

No

54

12

67

67

61

48

12

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/replace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/replace</a>
