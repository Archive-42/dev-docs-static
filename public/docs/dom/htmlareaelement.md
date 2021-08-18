# HTMLAreaElement

The `HTMLAreaElement` interface provides special properties and methods (beyond those of the regular object [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating the layout and presentation of [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) elements.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

[`HTMLElement.accessKey`](htmlelement/accesskey)  
Is a [`DOMString`](domstring) containing a single character that switches input focus to the control.

<span class="page-not-created">`HTMLAreaElement.alt`</span>  
Is a [`DOMString`](domstring) that reflects the [`alt`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-alt) HTML attribute, containing alternative text for the element.

<span class="page-not-created">`HTMLAreaElement.coords`</span>  
Is a [`DOMString`](domstring) that reflects the [`coords`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-coords) HTML attribute, containing coordinates to define the hot-spot region.

<span class="page-not-created">`HTMLAreaElement.download`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is a [`DOMString`](domstring) indicating that the linked resource is intended to be downloaded rather than displayed in the browser. The value represent the proposed name of the file. If the name is not a valid filename of the underlying OS, browser will adapt it.

[`HTMLAreaElement.hash`](htmlareaelement/hash)  
Is a [`USVString`](usvstring) containing the fragment identifier (including the leading hash mark (\#)), if any, in the referenced URL.

[`HTMLAreaElement.host`](htmlareaelement/host)  
Is a [`USVString`](usvstring) containing the hostname and port (if it's not the default port) in the referenced URL.

[`HTMLAreaElement.hostname`](htmlareaelement/hostname)  
Is a [`USVString`](usvstring) containing the hostname in the referenced URL.

[`HTMLAreaElement.href`](htmlareaelement/href)  
Is a [`USVString`](usvstring) containing that reflects the [`href`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-href) HTML attribute, containing a valid URL of a linked resource.

<span class="page-not-created">`HTMLAreaElement.noHref`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if the area is inactive (`true`) or active (`false`).

[`HTMLAreaElement.origin`](htmlareaelement/origin) <span class="badge inline readonly">Read only </span>  
Returns a [`USVString`](usvstring) containing the origin of the URL, that is its scheme, its domain and its port.

[`HTMLAreaElement.password`](htmlareaelement/password)  
Is a [`USVString`](usvstring) containing the password specified before the domain name.

[`HTMLAreaElement.pathname`](htmlareaelement/pathname)  
Is a [`USVString`](usvstring) containing the path name component, if any, of the referenced URL.

[`HTMLAreaElement.port`](htmlareaelement/port)  
Is a [`USVString`](usvstring) containing the port component, if any, of the referenced URL.

[`HTMLAreaElement.protocol`](htmlareaelement/protocol)  
Is a [`USVString`](usvstring) containing the protocol component (including trailing colon `':'`), of the referenced URL.

[`HTMLAreaElement.referrerPolicy`](htmlareaelement/referrerpolicy) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is a [`DOMString`](domstring) that reflects the [`referrerpolicy`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-referrerpolicy) HTML attribute indicating which referrer to use when fetching the linked resource.

[`HTMLAreaElement.rel`](htmlareaelement/rel)  
Is a [`DOMString`](domstring) that reflects the [`rel`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-rel) HTML attribute, indicating relationships of the current document to the linked resource.

[`HTMLAreaElement.relList`](htmlareaelement/rellist) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMTokenList`](domtokenlist) that reflects the [`rel`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-rel) HTML attribute, indicating relationships of the current document to the linked resource, as a list of tokens.

[`HTMLAreaElement.search`](htmlareaelement/search)  
Is a [`USVString`](usvstring) containing the search element (including leading question mark `'?'`), if any, of the referenced URL.

<span class="page-not-created">`HTMLAreaElement.shape`</span>  
Is a [`DOMString`](domstring) that reflects the [`shape`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-shape) HTML attribute, indicating the shape of the hot-spot, limited to known values.

[`HTMLOrForeignElement.tabIndex`](htmlorforeignelement/tabindex)  
Is a `long` containing the element's position in the tabbing order.

<span class="page-not-created">`HTMLAreaElement.target`</span>  
Is a [`DOMString`](domstring) that reflects the [`target`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-target) HTML attribute, indicating the browsing context in which to open the linked resource.

[`HTMLAreaElement.username`](htmlareaelement/username)  
Is a [`USVString`](usvstring) containing the username specified before the domain name.

## Methods

_Inherits methods from its parent, [`HTMLElement`](htmlelement)._

[`HTMLAreaElement.toString()`](htmlareaelement/tostring)  
Returns a [`USVString`](usvstring) containing the whole URL of the script executed in the [`Worker`](worker). It is a synonym for [`HTMLAreaElement.href`](htmlareaelement/href).

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlareaelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLAreaElement' in that specification.</span></a></td></tr></tbody></table>

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

`HTMLAreaElement`

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

`alt`

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

`coords`

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

`download`

54

13

20

No

41

10.1

54

54

20

41

10.3

6.0

`noHref`

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

14.1

53

53

50

41

14.5

7.2

`rel`

54

12

30

11

41

9

54

54

30

41

9

6.0

`relList`

65

18

30

No

41

9

65

65

30

41

9

9.0

`shape`

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

## See also

- HTML element implementing this interface: [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement</a>
