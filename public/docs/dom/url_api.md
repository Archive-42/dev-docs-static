URL API
=======

The URL API is a component of the URL standard, which defines what constitutes a valid [Uniform Resource Locator](https://developer.mozilla.org/en-US/docs/Glossary/URL) and the API that accesses and manipulates URLs. The URL standard also defines concepts such as domains, hosts, and IP addresses, and also attempts to describe in a standard way the legacy `application/x-www-form-urlencoded` [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) used to submit web forms' contents as a set of key/value pairs.

**Note:** This feature is available in [Web Workers](web_workers_api).

URL concepts and usage
----------------------

The majority of the URL standard is taken up by the [definition of a URL](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL) and how it is structured and parsed. Also covered are definitions of various terms related to addressing of computers on a network, and the algorithms for parsing IP addresses and DOM addresses are specified. More interesting to most developers is the API itself.

### Accessing URL components

Creating an [`URL`](url) object for a given URL parses the URL and provides quick access to its constituent parts through its properties.

    let addr = new URL("https://developer.mozilla.org/en-US/docs/Web/API/URL_API");
    let host = addr.host;
    let path = addr.pathname;

The snippet above creates a `URL` object for the article you're reading right now, then fetches the [`host`](url/host) and [`pathname`](url/pathname) properties. In this case, those strings are `developer.mozilla.org` and `/en-US/docs/Web/API/URL_API`, respectively.

### Changing the URL

Most of the properties of `URL` are settable; you can write new values to them to alter the URL represented by the object. For example, to create a URL and set its username:

    let myUsername = "someguy";
    let addr = new URL("https://mysite.com/login");
    addr.username = myUsername;

Setting the value of [`username`](url/username) not only sets that property's value, but it updates the overall URL. After executing the code snippet above, the value returned by [`addr.href`](url/href) is `https://someguy@mysite.com/login`. This is true for any of the writable properties.

### Queries

The [`search`](url/search) property on a `URL` contains the query string portion of the URL. For example, if the URL is `https://mysite.com/login?user=someguy&page=news`, then the value of the `search` property is `?user=someguy&page=news`. You can also look up the values of individual parameters with the [`URLSearchParams`](urlsearchparams) object's [`get()`](urlsearchparams/get) method:

    let addr = new URL("https://mysite.com/login?user=someguy&page=news");
    try {
      loginUser(addr.searchParams.get("user"));
      gotoPage(addr.searchParams.get("page"));
    } catch(err) {
      showErrorMessage(err);
    }

For example, in the above snippet, the username and target page are taken from the query and passed to appropriate functions that are used by the site's code to log in and route the user to their desired destination within the site.

Other functions within `URLSearchParams` let you change the value of keys, add and delete keys and their values, and even sort the list of parameters.

URL API interfaces
------------------

The URL API is a simple one, with only a couple of interfaces to its name:

-   <span class="indexListRow"><span class="indexListTerm">[`URL`](url)</span></span>
-   <span class="indexListRow"><span class="indexListTerm">[`URLSearchParams`](urlsearchparams)</span></span>

Older versions of the specification included an interface called [`URLUtilsReadOnly`](urlutilsreadonly), which has since been merged into the [`WorkerLocation`](workerlocation) interface.

Examples
--------

If you want to process the parameters included in a URL, you could do it manually, but it's much easier to create a `URL` object to do it for you. The `fillTableWithParameters()` function below takes as input a [`HTMLTableElement`](htmltableelement) object representing a [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table). Rows are added to the table, one for each key found in the parameters, with the first column containing the key's name, and the second column having the value.

Note the call to [`URLSearchParams.sort()`](urlsearchparams/sort) to sort the parameter list before generating the table.

    function fillTableWithParameters(tbl) {
      let url = new URL(document.location.href);
      url.searchParams.sort();
      let keys = url.searchParams.keys();

      for (let key of keys) {
        let val = url.searchParams.get(key);
        let row = document.createElement("tr");
        let cell = document.createElement("td");
        cell.innerText = key;
        row.appendChild(cell);
        cell = document.createElement("td");
        cell.innerText = val;
        row.appendChild(cell);
        tbl.appendChild(row);
      };
    }

A working version of this example can be [found on Glitch](https://url-api.glitch.me). Just add parameters to the URL when loading the page to see them in the table. For instance, try `https://url-api.glitch.me?from=mdn&excitement=high&likelihood=inconceivable`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/">URL</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG specification</td></tr></tbody></table>

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

`URL_API`

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

-   [Fetch API](fetch_api)
-   CSS [`<url>()`](https://developer.mozilla.org/en-US/docs/Web/CSS/url()) type

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL_API</a>
