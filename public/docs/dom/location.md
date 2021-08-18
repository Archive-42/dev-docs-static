# Location

The `Location` interface represents the location (URL) of the object it is linked to. Changes done on it are reflected on the object it relates to. Both the [`Document`](document) and [`Window`](window) interface have such a linked `Location`, accessible via [`Document.location`](document/location) and [`Window.location`](window/location) respectively.

## Anatomy Of Location

### HTML

    <span id="href"><span id="origin"><span id="protocol">http:</span>//<span id="host"><span id="hostname">example.org</span>:<span id="port">8888</span></span></span><span id="pathname">/foo/bar</span><span id="search">?q=baz</span><span id="hash">#bang</span></span>

### CSS

    html, body {height:100%;}
    html {display:table; width:100%;}
    body {display:table-cell; text-align:center; vertical-align:middle; font-family:georgia; font-size:230%; line-height:1em; white-space:nowrap;}

    [title] {position:relative; display:inline-block; box-sizing:border-box; /*border-bottom:.5em solid;*/ line-height:2em; cursor:pointer;}

    [title]:before {content:attr(title); font-family:monospace; position:absolute; top:100%; width:100%; left:50%; margin-left:-50%; font-size:40%; line-height:1.5; background:black;}
    [title]:hover:before,
    :target:before {background:black; color:yellow;}

    [title] [title]:before {margin-top:1.5em;}
    [title] [title] [title]:before {margin-top:3em;}
    [title] [title] [title] [title]:before {margin-top:4.5em;}

    [title]:hover,
    :target {position:relative; z-index:1; outline:50em solid rgba(255,255,255,.8);}

### JavaScript

    [].forEach.call(document.querySelectorAll('[title][id]'), function (node) {
      node.addEventListener("click", function(e) {
        e.preventDefault();
        e.stopPropagation();
        window.location.hash = '#' + e.target.getAttribute('id');
      });
    });
    [].forEach.call(document.querySelectorAll('[title]:not([id])'), function (node) {
      node.addEventListener("click", function(e) {
        e.preventDefault();
        e.stopPropagation();
        window.location.hash = '';
      });
    });

### Result

## Properties

[`Location.ancestorOrigins`](location/ancestororigins)  
Is a static [`DOMStringList`](domstringlist) containing, in reverse order, the origins of all ancestor browsing contexts of the document associated with the given `Location` object.

[`Location.href`](location/href)  
Is a stringifier that returns a [`USVString`](usvstring) containing the entire URL. If changed, the associated document navigates to the new page. It can be set from a different origin than the associated document.

[`Location.protocol`](location/protocol)  
Is a [`USVString`](usvstring) containing the protocol scheme of the URL, including the final `':'`.

[`Location.host`](location/host)  
Is a [`USVString`](usvstring) containing the host, that is the _hostname_, a `':'`, and the _port_ of the URL.

[`Location.hostname`](location/hostname)  
Is a [`USVString`](usvstring) containing the domain of the URL.

[`Location.port`](location/port)  
Is a [`USVString`](usvstring) containing the port number of the URL.

[`Location.pathname`](location/pathname)  
Is a [`USVString`](usvstring) containing an initial `'/'` followed by the path of the URL, not including the query string or fragment.

[`Location.search`](location/search)  
Is a [`USVString`](usvstring) containing a `'?'` followed by the parameters or "querystring" of the URL. Modern browsers provide [URLSearchParams](urlsearchparams/get#example) and [URL.searchParams](url/searchparams#example) to make it easy to parse out the parameters from the querystring.

[`Location.hash`](location/hash)  
Is a [`USVString`](usvstring) containing a `'#'` followed by the fragment identifier of the URL.

[`Location.origin`](location/origin) <span class="badge inline readonly">Read only </span>  
Returns a [`USVString`](usvstring) containing the canonical form of the origin of the specific location.

## Methods

[`Location.assign()`](location/assign)  
Loads the resource at the URL provided in parameter.

[`Location.reload()`](location/reload)  
Reloads the current URL, like the Refresh button.

[`Location.replace()`](location/replace)  
Replaces the current resource with the one at the provided URL (redirects to the provided URL). The difference from the `assign()` method and setting the `href` property is that after using `replace()` the current page will not be saved in session [`History`](history), meaning the user won't be able to use the _back_ button to navigate to it.

[`Location.toString()`](location/tostring)  
Returns a [`USVString`](usvstring) containing the whole URL. It is a synonym for [`HTMLAnchorElement.href`](htmlanchorelement/href), though it can't be used to modify the value.

## Examples

    // Create anchor element and use href property for the purpose of this example
    // A more correct alternative is to browse to the URL and use document.location or window.location
    var url = document.createElement('a');
    url.href = 'https://developer.mozilla.org:8080/en-US/search?q=URL#search-results-close-container';
    console.log(url.href);      // https://developer.mozilla.org:8080/en-US/search?q=URL#search-results-close-container
    console.log(url.protocol);  // https:
    console.log(url.host);      // developer.mozilla.org:8080
    console.log(url.hostname);  // developer.mozilla.org
    console.log(url.port);      // 8080
    console.log(url.pathname);  // /en-US/search
    console.log(url.search);    // ?q=URL
    console.log(url.hash);      // #search-results-close-container
    console.log(url.origin);    // https://developer.mozilla.org:8080

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#the-location-interface">HTML Living Standard<br />
<span class="small">The definition of 'Location' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`Location`

1

12

1

3

3

1

1

18

4

10.1

1

1.0

`ancestorOrigins`

20

79

No

No

15

6

4.4

25

No

14

6

1.5

`assign`

1

12

1

5.5

3

3

1

18

4

10.1

1

1.0

`hash`

1

12

1

3

≤12.1

1

1

18

4

≤12.1

1

1.0

`host`

1

12

1

3

≤12.1

1

1

18

4

≤12.1

1

1.0

`hostname`

1

12

1

3

≤12.1

1

1

18

4

≤12.1

1

1.0

`href`

1

12

1

3

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

12

21

Before Firefox 49, results for URL using the blob scheme incorrectly returned null.

11

Intranet sites are set to Compatibility View, which will emulate IE7 and omit `window.location.origin`.

15

5.1

≤37

18

21

Before Firefox 49, results for URL using the blob scheme incorrectly returned null.

14

5

1.0

`password`

No

No

26-45

No

No

No

No

No

26-45

No

No

No

`pathname`

1

12

1

Before Firefox 53, the `pathname` property returned wrong parts of the URL. For example, for a URL of http://z.com/x?a=true&b=false, `pathname` would return "/x?a=true&b=false" rather than "/x".

3

Internet Explorer does not provide the leading slash character in the `pathname` (`docs/Web/API/Location` instead of `/docs/Web/API/Location`).

≤12.1

1

1

18

4

Before Firefox 53, the `pathname` property returned wrong parts of the URL. For example, for a URL of http://z.com/x?a=true&b=false, `pathname` would return "/x?a=true&b=false" rather than "/x".

≤12.1

1

1.0

`port`

1

12

1

3

≤12.1

1

1

18

4

≤12.1

1

1.0

`protocol`

1

12

1

3

≤12.1

1

1

18

4

≤12.1

1

1.0

`reload`

1

12

Before Edge 79, if a page added to _Trusted Sites_ contains a cross-origin iframe, then calling `reload()` from within the iframe reloads the trusted page (in other words, the top page reloads, not the iframe).

1

5.5

If a page added to _Trusted Sites_ contains a cross-origin iframe, then calling `reload()` from within the iframe reloads the trusted page (in other words, the top page reloads, not the iframe).

3

1

1

18

4

10.1

1

1.0

`replace`

1

12

1

5.5

3

1

1

18

4

10.1

1

1.0

`search`

1

12

1

Before Firefox 53, the `search` property returned wrong parts of the URL. For example, for a URL of http://z.com/x?a=true&b=false, `search` would return "", rather than "?a=true&b=false".

3

≤12.1

1

1

18

4

Before Firefox 53, the `search` property returned wrong parts of the URL. For example, for a URL of http://z.com/x?a=true&b=false, `search` would return "", rather than "?a=true&b=false".

≤12.1

1

1.0

`toString`

52

12

22

11

Intranet sites are set to Compatibility View, which will emulate IE7 and omit `window.location.toString`.

?

1

52

52

22

?

1

6.0

`username`

No

No

26-45

No

No

No

No

No

26-45

No

No

No

## See also

- Two methods creating such an object: [`Window.location`](window/location) and [`Document.location`](document/location).
- URL related interfaces: [`URL`](url), [`URLSearchParams`](urlsearchparams) and <span class="page-not-created">`HTMLHyperlinkElementUtils`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location</a>
