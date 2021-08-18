# DOMTokenList

The `DOMTokenList` interface represents a set of space-separated tokens. Such a set is returned by [`Element.classList`](element/classlist), [`HTMLLinkElement.relList`](htmllinkelement/rellist), [`HTMLAnchorElement.relList`](htmlanchorelement/rellist), [`HTMLAreaElement.relList`](htmlareaelement/rellist), <span class="page-not-created">`HTMLIframeElement.sandbox`</span>, or <span class="page-not-created">`HTMLOutputElement.htmlFor`</span>. It is indexed beginning with `0` as with JavaScript [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) objects. `DOMTokenList` is always case-sensitive.

## Properties

[`DOMTokenList.length`](domtokenlist/length) <span class="badge inline readonly">Read only </span>  
Is an `integer` representing the number of objects stored in the object.

[`DOMTokenList.value`](domtokenlist/value)  
A stringifier property that returns the value of the list as a [`DOMString`](domstring).

## Methods

[`DOMTokenList.item(index)`](domtokenlist/item)  
Returns the item in the list by its `index`, or `undefined` if `index` is greater than or equal to the list's `length`.

[`DOMTokenList.contains(token)`](domtokenlist/contains)  
Returns `true` if the list contains the given `token`, otherwise `false`.

[`DOMTokenList.add(token1[, token2[, ...tokenN]])`](domtokenlist/add)  
Adds the specified `token`(s) to the list.

[`DOMTokenList.remove(token1[, token2[, ...tokenN]])`](domtokenlist/remove)  
Removes the specified `token`(s) from the list.

[`DOMTokenList.replace(oldToken, newToken)`](domtokenlist/replace)  
Replaces `token` with `newToken`.

[`DOMTokenList.supports(token)`](domtokenlist/supports)  
Returns `true` if a given `token` is in the associated attribute's supported tokens.

[`DOMTokenList.toggle(token [, force])`](domtokenlist/toggle)  
Removes `token` from the list if it exists, or adds `token` to the list if it doesn't. Returns a boolean indicating whether `token` is in the list after the operation.

[`DOMTokenList.entries()`](domtokenlist/entries)  
Returns an [iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols), allowing you to go through all key/value pairs contained in this object.

[`DOMTokenList.forEach(callback [, thisArg])`](domtokenlist/foreach)  
Executes a provided `callback` function once per `DOMTokenList` element.

[`DOMTokenList.keys()`](domtokenlist/keys)  
Returns an [iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols), allowing you to go through all keys of the key/value pairs contained in this object.

[`DOMTokenList.values()`](domtokenlist/values)  
Returns an [iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols), allowing you to go through all values of the key/value pairs contained in this object.

## Examples

In the following simple example, we retrieve the list of classes set on a [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) element as a `DOMTokenList` using [`Element.classList`](element/classlist), add a class using [`DOMTokenList.add()`](domtokenlist/add), and then update the [`Node.textContent`](node/textcontent) of the `<p>` to equal the `DOMTokenList`.

First, the HTML:

    <p class="a b c"></p>

Now the JavaScript:

    let para = document.querySelector("p");
    let classes = para.classList;
    para.classList.add("d");
    para.textContent = `paragraph classList is "${classes}"`;

The output looks like this:

## Trimming of whitespace and removal of duplicates

Methods that modify the `DOMTokenList` (such as [`DOMTokenList.add()`](domtokenlist/add)) automatically trim any excess [Whitespace](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace) and remove duplicate values from the list. For example:

    <span class="    d   d e f"></span>

    let span = document.querySelector("span");
    let classes = span.classList;
    span.classList.add("x");
    span.textContent = `span classList is "${classes}"`;

The output looks like this:

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-domtokenlist">DOM<br />
<span class="small">The definition of 'DOMTokenList' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`DOMTokenList`

8

12

3.6

10

11.5

5.1

3

18

4

11.5

5.1

1.0

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

`entries`

42

16

50

No

32

10.1

45

45

50

32

10.3

5.0

`forEach`

42

16

50

No

32

10.1

45

45

50

32

10.3

5.0

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

`keys`

42

16

50

No

32

10.1

45

45

50

32

10.3

5.0

`length`

8

12

50

10

Yes

5.1

3

18

50

Yes

5.1

1.0

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

`remove_duplicates`

60

17

55

No

47

10

60

60

55

44

10

8.0

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

`supports`

49

17

49

No

36

10.1

49

49

49

36

10.3

5.0

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

`trim_whitespace`

48

12

51

10

35

10

48

48

51

35

10

5.0

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

`values`

42

16

50

No

32

10.1

45

45

50

32

10.3

5.0

`@@iterator`

42

16

36

No

29

10.1

42

42

36

29

10.3

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList</a>
