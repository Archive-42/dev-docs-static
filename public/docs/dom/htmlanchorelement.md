HTMLAnchorElement
=================

The `HTMLAnchorElement` interface represents hyperlink elements and provides special properties and methods (beyond those of the regular [`HTMLElement`](htmlelement) object interface that they inherit from) for manipulating the layout and presentation of such elements. This interface corresponds to `<a>` element; not to be confused with `<link>`, which is represented by `HTMLLinkElement`)

Properties
----------

*Inherits properties from its parent, [`HTMLElement`](htmlelement).*

[`HTMLElement.accessKey`](htmlelement/accesskey)  
Is a [`DOMString`](domstring) representing a single character that switches input focus to the hyperlink.

 [`HTMLAnchorElement.download`](htmlanchorelement/download) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Is a [`DOMString`](domstring) indicating that the linked resource is intended to be downloaded rather than displayed in the browser. The value represent the proposed name of the file. If the name is not a valid filename of the underlying OS, browser will adapt it.

[`HTMLAnchorElement.hash`](htmlanchorelement/hash)  
Is a [`USVString`](usvstring) representing the fragment identifier, including the leading hash mark ('`#`'), if any, in the referenced URL.

[`HTMLAnchorElement.host`](htmlanchorelement/host)  
Is a [`USVString`](usvstring) representing the hostname and port (if it's not the default port) in the referenced URL.

[`HTMLAnchorElement.hostname`](htmlanchorelement/hostname)  
Is a [`USVString`](usvstring) representing the hostname in the referenced URL.

[`HTMLAnchorElement.href`](htmlanchorelement/href)  
Is a [`USVString`](usvstring) that is the result of parsing the [`href`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-href) HTML attribute relative to the document, containing a valid URL of a linked resource.

<span class="page-not-created">`HTMLAnchorElement.hreflang`</span>  
Is a [`DOMString`](domstring) that reflects the [`hreflang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-hreflang) HTML attribute, indicating the language of the linked resource.

 [`HTMLAnchorElement.origin`](htmlanchorelement/origin) <span class="badge inline readonly">Read only </span>   
Returns a [`USVString`](usvstring) containing the origin of the URL, that is its scheme, its domain and its port.

[`HTMLAnchorElement.password`](htmlanchorelement/password)  
Is a [`USVString`](usvstring) containing the password specified before the domain name.

[`HTMLAnchorElement.pathname`](htmlanchorelement/pathname)  
Is a [`USVString`](usvstring) containing an initial `'/'` followed by the path of the URL, not including the query string or fragment.

[`HTMLAnchorElement.port`](htmlanchorelement/port)  
Is a [`USVString`](usvstring) representing the port component, if any, of the referenced URL.

[`HTMLAnchorElement.protocol`](htmlanchorelement/protocol)  
Is a [`USVString`](usvstring) representing the protocol component, including trailing colon ('`:`'), of the referenced URL.

 [`HTMLAnchorElement.referrerPolicy`](htmlanchorelement/referrerpolicy) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Is a [`DOMString`](domstring) that reflects the [`referrerpolicy`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-referrerpolicy) HTML attribute indicating which referrer to use.

[`HTMLAnchorElement.rel`](htmlanchorelement/rel)  
Is a [`DOMString`](domstring) that reflects the [`rel`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-rel) HTML attribute, specifying the relationship of the target object to the linked object.

 [`HTMLAnchorElement.relList`](htmlanchorelement/rellist) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMTokenList`](domtokenlist) that reflects the [`rel`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-rel) HTML attribute, as a list of tokens.

[`HTMLAnchorElement.search`](htmlanchorelement/search)  
Is a [`USVString`](usvstring) representing the search element, including leading question mark ('`?`'), if any, of the referenced URL.

[`HTMLOrForeignElement.tabIndex`](htmlorforeignelement/tabindex)  
Is a `long` containing the position of the element in the tabbing navigation order for the current document.

<span class="page-not-created">`HTMLAnchorElement.target`</span>  
Is a [`DOMString`](domstring) that reflects the [`target`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-target) HTML attribute, indicating where to display the linked resource.

<span class="page-not-created">`HTMLAnchorElement.text`</span>  
Is a [`DOMString`](domstring) being a synonym for the [`Node.textContent`](node/textcontent) property.

<span class="page-not-created">`HTMLAnchorElement.type`</span>  
Is a [`DOMString`](domstring) that reflects the [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-type) HTML attribute, indicating the MIME type of the linked resource.

[`HTMLAnchorElement.username`](htmlanchorelement/username)  
Is a [`USVString`](usvstring) containing the username specified before the domain name.

### Obsolete properties

 <span class="page-not-created">`HTMLAnchorElement.charset`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) representing the character encoding of the linked resource.

 <span class="page-not-created">`HTMLAnchorElement.coords`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) representing a comma-separated list of coordinates.

 <span class="page-not-created">`HTMLAnchorElement.name`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) representing the anchor name.

 <span class="page-not-created">`HTMLAnchorElement.rev`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) representing that the [`rev`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-rev) HTML attribute, specifying the relationship of the link object to the target object.

**Note**: Currently the W3C HTML 5.2 spec states that `rev` is no longer obsolete, whereas the WHATWG living standard still has it labeled obsolete. Until this discrepancy is resolved, you should still assume it is obsolete.

 <span class="page-not-created">`HTMLAnchorElement.shape`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) representing the shape of the active area.

Methods
-------

*Inherits methods from its parent, [`HTMLElement`](htmlelement).*

[`HTMLOrForeignElement.blur`](htmlorforeignelement/blur)  
Removes the keyboard focus from the current element.

[`HTMLOrForeignElement.focus`](htmlorforeignelement/focus)  
Gives the keyboard focus to the current element.

[`HTMLAnchorElement.toString()`](htmlanchorelement/tostring)  
Returns a [`USVString`](usvstring) containing the whole URL. It is a synonym for [`HTMLAnchorElement.href`](htmlanchorelement/href), though it can't be used to modify the value.

The `blur()` and `focus()` methods are inherited from [`HTMLElement`](htmlelement) from HTML5 on, but were defined on `HTMLAnchorElement` in DOM Level 2 HTML and earlier specifications.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlanchorelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLAnchorElement' in that specification.</span></a></td></tr></tbody></table>

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

`HTMLAnchorElement`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`charset`

1

12

1

6

≤12.1

3

1

18

4

≤12.1

1

1.0

`coords`

1

12

1

6

≤12.1

3

1

18

4

≤12.1

1

1.0

`download`

15

13

20

No

15

10.1

≤37

18

20

14

10.3

1.0

`hreflang`

1

12

1

6

≤12.1

3

1

18

4

≤12.1

1

1.0

`name`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`ping`

12

17

3

No

15

5.1

≤37

18

4

14

5

1.0

`referrerPolicy`

53

79

50

No

40

14

53

53

50

41

14

7.2

`rel`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`relList`

65

18

30

No

52

9

65

65

30

47

9

9.0

`rev`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`shape`

1

12

1

6

≤12.1

3

1

18

4

≤12.1

1

1.0

`target`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`text`

1

12

1

10

≤12.1

3

1

18

4

≤12.1

1

1.0

`type`

1

12

1

6

≤12.1

3

1

18

4

≤12.1

1

1.0

`hash`

1

12

1

From Firefox 29 to Firefox 40, the returned value was incorrectly percent-decoded.

5

15

1

1

18

4

From Firefox 29 to Firefox 40, the returned value was incorrectly percent-decoded.

14

1

1.0

`host`

1

12

1

5

In Internet Explorer 9, the host of an [`<a>`](https://developer.mozilla.org/docs/Web/HTML/Element/a) always include the port (e.g. `developer.mozilla.org:443`), even if there is no explicit port in the `href` attribute value.

15

1

1

18

4

14

1

1.0

`hostname`

1

12

1

5

15

1

1

18

4

14

1

1.0

`href`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

`origin`

8

17

26

Before Firefox 49, results for URL using the `blob` scheme incorrectly returned `null`.

No

15

5.1

≤37

18

26

Before Firefox 49, results for URL using the `blob` scheme incorrectly returned `null`.

14

5

1.0

`password`

32

79

26

No

19

10

4.4.3

32

26

19

10

2.0

`pathname`

1

12

1

Before Firefox 53, the `pathname` and `search` `HTMLHyperlinkElementUtils` properties returned the wrong parts of the URL. For example, for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return `'/x?a=true&b=false'` and `search` would return '', rather than `'/x'` and `'?a=true&b=false'` respectively. This has now been fixed.

5

15

1

1

18

4

Before Firefox 53, the `pathname` and `search` `HTMLHyperlinkElementUtils` properties returned the wrong parts of the URL. For example, for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return `'/x?a=true&b=false'` and `search` would return '', rather than `'/x'` and `'?a=true&b=false'` respectively. This has now been fixed.

14

1

1.0

`port`

1

12

1

5

15

1

1

18

4

14

1

1.0

`protocol`

1

12

1

5

15

1

1

18

4

14

1

1.0

`search`

1

12

1

Before Firefox 53, the `pathname` and `search` `HTMLHyperlinkElementUtils` properties returned the wrong parts of the URL. For example, for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return `'/x?a=true&b=false'` and `search` would return '', rather than `'/x'` and `'?a=true&b=false'` respectively. This has now been fixed.

5

15

1

1

18

4

Before Firefox 53, the `pathname` and `search` `HTMLHyperlinkElementUtils` properties returned the wrong parts of the URL. For example, for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return `'/x?a=true&b=false'` and `search` would return '', rather than `'/x'` and `'?a=true&b=false'` respectively. This has now been fixed.

14

1

1.0

`toString`

52

≤18

22

No

Yes

Yes

52

52

22

Yes

Yes

6.0

`username`

32

79

26

No

19

10

4.4.3

32

26

19

10

2.0

See also
--------

-   The HTML element implementing this interface: [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement</a>
