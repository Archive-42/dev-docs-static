URLSearchParams
===============

The `URLSearchParams` interface defines utility methods to work with the query string of a URL.

An object implementing `URLSearchParams` can directly be used in a [`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) structure, for example the following two lines are equivalent:

    for (const [key, value] of mySearchParams) {}
    for (const [key, value] of mySearchParams.entries()) {}

**Note:** This feature is available in [Web Workers](web_workers_api).

Constructor
-----------

[`URLSearchParams()`](urlsearchparams/urlsearchparams)  
Returns a `URLSearchParams` object instance.

Methods
-------

[`URLSearchParams.append()`](urlsearchparams/append)  
Appends a specified key/value pair as a new search parameter.

[`URLSearchParams.delete()`](urlsearchparams/delete)  
Deletes the given search parameter, and its associated value, from the list of all search parameters.

[`URLSearchParams.entries()`](urlsearchparams/entries)  
Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing iteration through all key/value pairs contained in this object.

[`URLSearchParams.forEach()`](urlsearchparams/foreach)  
Allows iteration through all values contained in this object via a callback function.

[`URLSearchParams.get()`](urlsearchparams/get)  
Returns the first value associated with the given search parameter.

[`URLSearchParams.getAll()`](urlsearchparams/getall)  
Returns all the values associated with a given search parameter.

[`URLSearchParams.has()`](urlsearchparams/has)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if such a given parameter exists.

[`URLSearchParams.keys()`](urlsearchparams/keys)  
Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing iteration through all keys of the key/value pairs contained in this object.

[`URLSearchParams.set()`](urlsearchparams/set)  
Sets the value associated with a given search parameter to the given value. If there are several values, the others are deleted.

[`URLSearchParams.sort()`](urlsearchparams/sort)  
Sorts all key/value pairs, if any, by their keys.

[`URLSearchParams.toString()`](urlsearchparams/tostring)  
Returns a string containing a query string suitable for use in a URL.

[`URLSearchParams.values()`](urlsearchparams/values)  
Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing iteration through all values of the key/value pairs contained in this object.

Examples
--------

    var paramsString = "q=URLUtils.searchParams&topic=api";
    var searchParams = new URLSearchParams(paramsString);

    //Iterate the search parameters.
    for (let p of searchParams) {
      console.log(p);
    }

    searchParams.has("topic") === true; // true
    searchParams.get("topic") === "api"; // true
    searchParams.getAll("topic"); // ["api"]
    searchParams.get("foo") === null; // true
    searchParams.append("topic", "webdev");
    searchParams.toString(); // "q=URLUtils.searchParams&topic=api&topic=webdev"
    searchParams.set("topic", "More webdev");
    searchParams.toString(); // "q=URLUtils.searchParams&topic=More+webdev"
    searchParams.delete("topic");
    searchParams.toString(); // "q=URLUtils.searchParams"

### Gotchas

The `URLSearchParams` constructor does *not* parse full URLs. However, it will strip an initial leading `?` off of a string, if present.

    var paramsString1 = "http://example.com/search?query=%40";
    var searchParams1 = new URLSearchParams(paramsString1);

    searchParams1.has("query"); // false
    searchParams1.has("http://example.com/search?query"); // true

    searchParams1.get("query"); // null
    searchParams1.get("http://example.com/search?query"); // "@" (equivalent to decodeURIComponent('%40'))

    var paramsString2 = "?query=value";
    var searchParams2 = new URLSearchParams(paramsString2);
    searchParams2.has("query"); // true

    var url = new URL("http://example.com/search?query=%40");
    var searchParams3 = new URLSearchParams(url.search);
    searchParams3.has("query") // true

    let base64 = btoa(String.fromCharCode(19,224,23,64,31,128)); // base64 is "E+AXQB+A"
    let searchParams = new URLSearchParams("q=foo&bin=" + base64); // q=foo&bin=E+AXQB+A
    let getBin = searchParams.get("bin"); // "E AXQB A" + char is replaced by spaces
    btoa(atob(getBin)); // "EAXQBA==" no error thrown
    btoa(String.fromCharCode(16,5,208,4)) // "EAXQBA==" decodes to wrong binary value
    getBin.replace(//g, "+"); // "E+AXQB+A" is one solution

    // or use set to add the parameter, but this increases the query string length
    searchParams.set("bin2", base64) // "q=foo&bin=E+AXQB+A&bin2=E%2BAXQB%2BA" encodes + as %2B
    searchParams.get("bin2"); // "E+AXQB+A"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#urlsearchparams">URL<br />
<span class="small">The definition of 'URLSearchParams' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`URLSearchParams`

49

17

29

Prior to version 57 single quotes in URLs were escaped (see [bug 1386683](https://bugzil.la/1386683)).

No

36

10.1

49

49

29

Prior to version 57 single quotes in URLs were escaped (see [bug 1386683](https://bugzil.la/1386683)).

36

10.3

5.0

`URLSearchParams`

49

17

29

No

36

10.1

49

49

29

36

10.3

5.0

`append`

49

17

29

No

36

10.1

49

49

29

36

10.3

5.0

`delete`

49

17

29

No

36

Yes

Removing a non-existent query parameter doesn't remove `?` from the URL. See [bug 193022](https://webkit.org/b/193022).

49

49

29

36

Yes

Removing a non-existent query parameter doesn't remove `?` from the URL. See [bug 193022](https://webkit.org/b/193022).

5.0

`entries`

49

17

44

No

36

Yes

49

49

44

36

Yes

5.0

`forEach`

49

17

44

No

36

Yes

49

49

44

36

Yes

5.0

`get`

49

17

29

No

36

Yes

49

49

29

36

Yes

5.0

`getAll`

49

17

29

No

36

Yes

49

49

29

36

Yes

5.0

`has`

49

17

29

No

36

Yes

49

49

29

36

Yes

5.0

`keys`

49

17

44

No

36

Yes

49

49

44

36

Yes

5.0

`set`

49

17

29

No

36

Yes

49

49

29

36

Yes

5.0

`sort`

61

17

54

No

48

Yes

61

61

54

45

Yes

8.0

`toString`

49

17

29

No

36

Yes

49

49

29

36

Yes

5.0

`values`

49

17

44

No

36

Yes

49

49

44

36

Yes

5.0

`@@iterator`

49

17

44

No

36

10.1

49

49

44

36

10.3

5.0

See also
--------

-   The [`URL`](url) interface.
-   [Google Developers: Easy URL manipulation with URLSearchParams](https://developers.google.com/web/updates/2016/01/urlsearchparams?hl=en)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams</a>
