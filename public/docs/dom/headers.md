Headers
=======

The `Headers` interface of the [Fetch API](fetch_api) allows you to perform various actions on [HTTP request and response headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers). These actions include retrieving, setting, adding to, and removing headers from the list of the request's headers. A `Headers` object has an associated header list, which is initially empty and consists of zero or more name and value pairs. You can add to this using methods like [`append()`](headers/append) (see [Examples](#examples).) In all methods of this interface, header names are matched by case-insensitive byte sequence.

For security reasons, some headers can only be controlled by the user agent. These headers include the [forbidden header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name) and [forbidden response header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_response_header_name).

A Headers object also has an associated guard, which takes a value of `immutable`, `request`, `request-no-cors`, `response`, or `none`. This affects whether the [`set()`](headers/set), [`delete()`](headers/delete), and [`append()`](headers/append) methods will mutate the header. For more information see [Guard](https://developer.mozilla.org/en-US/docs/Glossary/Guard).

You can retrieve a `Headers` object via the [`Request.headers`](request/headers) and [`Response.headers`](response/headers) properties, and create a new `Headers` object using the [`Headers.Headers()`](headers/headers) constructor.

An object implementing `Headers` can directly be used in a [`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) structure, instead of [`entries()`](headers/entries): `for (var p of myHeaders)` is equivalent to `for (var p of myHeaders.entries())`.

**Note**: you can find more out about the available headers by reading our [HTTP headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers) reference.

Constructor
-----------

[`Headers()`](headers/headers)  
Creates a new `Headers` object.

Methods
-------

[`Headers.append()`](headers/append)  
Appends a new value onto an existing header inside a `Headers` object, or adds the header if it does not already exist.

[`Headers.delete()`](headers/delete)  
Deletes a header from a `Headers` object.

[`Headers.entries()`](headers/entries)  
Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing to go through all key/value pairs contained in this object.

<span class="page-not-created">`Headers.forEach()`</span>  
Executes a provided function once for each array element.

[`Headers.get()`](headers/get)  
Returns a [`ByteString`](bytestring) sequence of all the values of a header within a `Headers` object with a given name.

[`Headers.has()`](headers/has)  
Returns a boolean stating whether a `Headers` object contains a certain header.

[`Headers.keys()`](headers/keys)  
Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing you to go through all keys of the key/value pairs contained in this object.

[`Headers.set()`](headers/set)  
Sets a new value for an existing header inside a `Headers` object, or adds the header if it does not already exist.

[`Headers.values()`](headers/values)  
Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing you to go through all values of the key/value pairs contained in this object.

**Note**: To be clear, the difference between [`Headers.set()`](headers/set) and [`Headers.append()`](headers/append) is that if the specified header does already exist and does accept multiple values, [`Headers.set()`](headers/set) will overwrite the existing value with the new one, whereas [`Headers.append()`](headers/append) will append the new value onto the end of the set of values. See their dedicated pages for example code.

**Note**: All of the Headers methods will throw a `TypeError` if you try to pass in a reference to a name that isn't a [valid HTTP Header name](https://fetch.spec.whatwg.org/#concept-header-name). The mutation operations will throw a `TypeError` if the header has an immutable [Guard](https://developer.mozilla.org/en-US/docs/Glossary/Guard). In any other failure case they fail silently.

**Note**: When Header values are iterated over, they are automatically sorted in lexicographical order, and values from duplicate header names are combined.

### Obsolete methods

[`Headers.getAll()`](headers/getall)  
Used to return an array of all the values of a header within a `Headers` object with a given name; this method has now been deleted from the spec, and [`Headers.get()`](headers/get) now returns all values of a given name instead of just the first one.

Examples
--------

In the following snippet, we create a new header using the `Headers()` constructor, add a new header to it using `append()`, then return that header value using `get()`:

    var myHeaders = new Headers();

    myHeaders.append('Content-Type', 'text/xml');
    myHeaders.get('Content-Type') // should return 'text/xml'

The same can be achieved by passing an array of arrays or an object literal to the constructor:

    var myHeaders = new Headers({
        'Content-Type': 'text/xml'
    });

    // or, using an array of arrays:
    myHeaders = new Headers([
        ['Content-Type', 'text/xml']
    ]);

    myHeaders.get('Content-Type') // should return 'text/xml'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#headers-class">Fetch<br />
<span class="small">The definition of 'Headers' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`Headers`

42

41

14

39

34

No

29

28

10.1

42

42

41

44

29

28

10.3

4.0

`Headers`

42

41

14

39

34

No

29

28

10.1

42

42

41

No

29

28

10.3

4.0

`append`

42

41

14

39

34

No

29

28

10.1

42

42

41

No

29

28

10.3

4.0

`delete`

42

41

14

39

34

No

29

28

10.1

42

42

41

No

29

28

10.3

4.0

`entries`

45

16

44

No

32

10.1

45

45

44

32

10.3

5.0

`forEach`

42

14

47

No

29

10.1

42

42

47

29

10.3

4.0

`get`

42

41

14

52

Prior to Firefox 52, `get()` only returned the first value in the specified header, with `getAll()` returning all values. From 52 onwards, `get()` now returns all values and `getAll()` has been deleted.

39

34

No

29

28

10.1

42

42

41

No

29

28

10.3

4.0

`getAll`

42-60

≤18-79

39-52

34

No

29-47

No

42-60

42-60

No

29-44

No

4.0

`has`

42

41

14

39

34

No

29

28

10.1

42

42

41

No

29

28

10.3

4.0

`keys`

45

16

44

No

32

10.1

45

45

44

32

10.3

5.0

`lexicographical_sorting`

?

?

44

No

28

No

?

?

No

?

No

?

`set`

42

41

14

39

34

No

29

28

10.1

42

42

41

No

29

28

10.3

4.0

`values`

45

16

44

No

32

10.1

45

45

44

32

10.3

5.0

`@@iterator`

42

16

44

No

29

10.1

42

42

44

29

10.3

4.0

See also
--------

-   [ServiceWorker API](service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Headers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Headers</a>
