URL
===

The `URL` interface is used to parse, construct, normalize, and encode [URLs](https://developer.mozilla.org/en-US/docs/Glossary/URL). It works by providing properties which allow you to easily read and modify the components of a URL. You normally create a new `URL` object by specifying the URL as a string when calling its constructor, or by providing a relative URL and a base URL. You can then easily read the parsed components of the URL or make changes to the URL.

If a browser doesn't yet support the [`URL()`](url/url) constructor, you can access a URL object using the [`Window`](window) interface's [`URL`](url) property. Be sure to check to see if any of your target browsers require this to be prefixed.

**Note:** This feature is available in [Web Workers](web_workers_api).

Constructor
-----------

[`new URL()`](url/url)  
Creates and returns a `URL` object referencing the URL specified using an absolute URL string, or a relative URL string and a base URL string.

Properties
----------

[`hash`](url/hash)  
A [`USVString`](usvstring) containing a `'#'` followed by the fragment identifier of the URL.

[`host`](url/host)  
A [`USVString`](usvstring) containing the domain (that is the *hostname*) followed by (if a port was specified) a `':'` and the *port* of the URL.

[`hostname`](url/hostname)  
A [`USVString`](usvstring) containing the domain of the URL.

[`href`](url/href)  
A stringifier that returns a [`USVString`](usvstring) containing the whole URL.

 [`origin`](url/origin) <span class="badge inline readonly">Read only </span>   
Returns a [`USVString`](usvstring) containing the origin of the URL, that is its scheme, its domain and its port.

[`password`](url/password)  
A [`USVString`](usvstring) containing the password specified before the domain name.

[`pathname`](url/pathname)  
Is a [`USVString`](usvstring) containing an initial `'/'` followed by the path of the URL, not including the query string or fragment.

[`port`](url/port)  
A [`USVString`](usvstring) containing the port number of the URL.

[`protocol`](url/protocol)  
A [`USVString`](usvstring) containing the protocol scheme of the URL, including the final `':'`.

[`search`](url/search)  
A [`USVString`](usvstring) indicating the URL's parameter string; if any parameters are provided, this string includes all of them, beginning with the leading `?` character.

 [`searchParams`](url/searchparams) <span class="badge inline readonly">Read only </span>   
A [`URLSearchParams`](urlsearchparams) object which can be used to access the individual query parameters found in `search`.

[`username`](url/username)  
A [`USVString`](usvstring) containing the username specified before the domain name.

Methods
-------

[`toString()`](url/tostring)  
Returns a [`USVString`](usvstring) containing the whole URL. It is a synonym for [`URL.href`](url/href), though it can't be used to modify the value.

[`toJSON()`](url/tojson)  
Returns a [`USVString`](usvstring) containing the whole URL. It returns the same string as the `href` property.

Static methods
--------------

[`createObjectURL()`](url/createobjecturl)  
Returns a [`DOMString`](domstring) containing a unique blob URL, that is a URL with `blob:` as its scheme, followed by an opaque string uniquely identifying the object in the browser.

[`revokeObjectURL()`](url/revokeobjecturl)  
Revokes an object URL previously created using [`URL.createObjectURL()`](url/createobjecturl).

Usage notes
-----------

The constructor takes a `url` parameter, and an optional `base` parameter to use as a base if the `url` parameter is a relative URL:

    const url = new URL('../cats', 'http://www.example.com/dogs');
    console.log(url.hostname); // "www.example.com"
    console.log(url.pathname); // "/cats"

URL properties can be set to construct the URL:

    url.hash = 'tabby';
    console.log(url.href); // "http://www.example.com/cats#tabby"

URLs are encoded according to the rules found in [RFC 3986](https://tools.ietf.org/html/rfc3986). For instance:

    url.pathname = 'démonstration.html';
    console.log(url.href); // "http://www.example.com/d%C3%A9monstration.html"

The [`URLSearchParams`](urlsearchparams) interface can be used to build and manipulate the URL query string.

To get the search params from the current window's URL, you can do this:

    // https://some.site/?id=123
    const parsedUrl = new URL(window.location.href);
    console.log(parsedUrl.searchParams.get("id")); // "123"

The [`toString()`](url/tostring) method of `URL` just returns the value of the [`href`](url/href) property, so the constructor can be used to normalize and encode a URL directly.

    const response = await fetch(new URL('http://www.example.com/démonstration.html'));

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#creating-revoking">File API<br />
<span class="small">The definition of 'URL' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the static methods <code>URL.createObjectURL()</code> and <code>URL.revokeObjectURL</code><code>()</code>.</td></tr><tr class="even"><td><a href="https://url.spec.whatwg.org/#api">URL<br />
<span class="small">The definition of 'API' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition (implements <code>URLUtils</code>).</td></tr></tbody></table>

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

`URL`

32

19

12

19

\["Before version 57, Firefox had a bug whereby single quotes contained in URLs are escaped when accessed via URL APIs (see [bug 1386683](https://bugzil.la/1386683)).", "To use it from chrome code, JSM and Bootstrap scope, you have to import it with `Cu.importGlobalProperties(['URL']);`."\]

10

19

15

7

6

4.4

4

32

25

19

\["Before version 57, Firefox had a bug whereby single quotes contained in URLs are escaped when accessed via URL APIs (see [bug 1386683](https://bugzil.la/1386683)).", "To use it from chrome code, JSM and Bootstrap scope, you have to import it with `Cu.importGlobalProperties(['URL']);`."\]

19

14

7

6

2.0

1.5

`URL`

19

12

26

No

15

6

In Safari 14 and earlier, calling the `URL` constructor with a base URL whose value is `undefined` causes Safari to throw a `TypeError`; see [WebKit bug 216841](https://webkit.org/b/216841).

≤37

25

26

14

6

In Safari 14 and earlier, calling the `URL` constructor with a base URL whose value is `undefined` causes Safari to throw a `TypeError`; see [WebKit bug 216841](https://webkit.org/b/216841).

1.5

`createObjectURL`

19

12

19

`createObjectURL()` is no longer available within the context of a `ServiceWorker`.

10

If the underlying object does not have a content type set, using this URL as the `src` of an `img` tag fails intermittently with error DOM7009.

15

6

≤37

25

19

`createObjectURL()` is no longer available within the context of a `ServiceWorker`.

14

6

1.5

`hash`

32

13

22

No

19

7

4.4.3

32

22

19

7

2.0

`host`

32

13

22

No

19

7

4.4.3

32

22

19

7

2.0

`hostname`

32

13

22

No

19

10

4.4.3

32

22

19

Yes

2.0

`href`

32

13

22

No

19

10

4.4.3

32

22

19

Yes

2.0

`origin`

32

12

26

26-49

Results for `URL` using the `blob` scheme incorrectly returned `null`.

No

19

10

≤37

32

26

26-49

Results for `URL` using the `blob` scheme incorrectly returned `null`.

19

Yes

6.0

`password`

32

12

26

No

19

10

≤37

32

26

19

Yes

6.0

`pathname`

32

13

53

22-53

`pathname` and `search` returned the wrong values so that for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return "/x?a=true&b=false" and `search` would return "", rather than "/x" and "?a=true&b=false" respectively.

No

19

10

4.4.3

32

53

22-53

`pathname` and `search` returned the wrong values so that for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return "/x?a=true&b=false" and `search` would return "", rather than "/x" and "?a=true&b=false" respectively.

19

Yes

2.0

`port`

32

13

22

No

19

10

4.4.3

32

22

19

Yes

2.0

`protocol`

32

13

22

No

19

10

4.4.3

32

22

19

Yes

2.0

`revokeObjectURL`

19

12

19

`revokeObjectURL()` is no longer available within the context of a `ServiceWorker`.

10

15

6

≤37

25

19

`revokeObjectURL()` is no longer available within the context of a `ServiceWorker`.

14

6

1.5

`search`

32

13

53

22-53

`pathname` and `search` returned the wrong values so that for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return "/x?a=true&b=false" and `search` would return "", rather than "/x" and "?a=true&b=false" respectively.

No

19

10

4.4.3

32

53

22-53

`pathname` and `search` returned the wrong values so that for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return "/x?a=true&b=false" and `search` would return "", rather than "/x" and "?a=true&b=false" respectively.

19

Yes

2.0

`searchParams`

51

17

29

No

38

10

51

51

29

41

10

5.0

`toJSON`

71

17

54

No

58

11

71

71

54

50

11

10.0

`toString`

19

17

54

No

15

6.1

≤37

25

54

14

6.1

6.0

`username`

32

12

26

No

19

10

≤37

32

26

19

Yes

6.0

See also
--------

-   [URL API](url_api)
-   [What is a URL?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL)
-   Property to obtain a `URL` object: [`URL`](url).
-   [`URLSearchParams`](urlsearchparams).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL</a>
