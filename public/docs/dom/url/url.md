URL()
=====

The `URL()` constructor returns a newly created [`URL`](../url) object representing the URL defined by the parameters.

If the given base URL or the resulting URL are not valid URLs, the JavaScript [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) exception is thrown.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    const url = new URL(url [, base])

### Parameters

`url`  
A [`USVString`](../usvstring) or any other object with a [stringifier](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Howto/Write_an_API_reference/Information_contained_in_a_WebIDL_file#stringifiers) — including, for example, an [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) or [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) element — that represents an absolute or relative URL. If `url` is a relative URL, `base` is required, and will be used as the base URL. If `url` is an absolute URL, a given `base` will be ignored.

 `base` <span class="badge inline optional">Optional</span>   
A [`USVString`](../usvstring) representing the base URL to use in cases where `url` is a relative URL. If not specified, it defaults to `undefined`.

**Note**: The `url` and `base` arguments will each be stringified from whatever value you pass, just like with other Web APIs that accept [`USVString`](../usvstring). In particular, you can use an existing [`URL`](../url) object for either argument, and it will stringify to the object's [`href`](href) property.

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError"><code>TypeError</code></a></td><td><code>url</code> (in the case of absolute URLs) or <code>base</code> + <code>url</code> (in the case of relative URLs) is not a valid URL.</td></tr></tbody></table>

Examples
--------

    // Base urls
    let m = 'https://developer.mozilla.org';
    let a = new URL("/", m);                                // => 'https://developer.mozilla.org/'
    let b = new URL(m);                                     // => 'https://developer.mozilla.org/'

            new URL('en-US/docs', b);                      // => 'https://developer.mozilla.org/en-US/docs'
    let d = new URL('/en-US/docs', b);                     // => 'https://developer.mozilla.org/en-US/docs'
            new URL('/en-US/docs', d);                     // => 'https://developer.mozilla.org/en-US/docs'
            new URL('/en-US/docs', a);                     // => 'https://developer.mozilla.org/en-US/docs'

            new URL('/en-US/docs', "https://developer.mozilla.org/fr-FR/toto");
                                                           // => 'https://developer.mozilla.org/en-US/docs'

            new URL('/en-US/docs', '');                    // Raises a TypeError exception as '' is not a valid URL
            new URL('/en-US/docs');                        // Raises a TypeError exception as '/en-US/docs' is not a valid URL
            new URL('http://www.example.com', );           // => 'http://www.example.com/'
            new URL('http://www.example.com', b);          // => 'http://www.example.com/'

            new URL("//foo.com", "https://example.com")    // => 'https://foo.com' (see relative URLs)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#constructors">URL<br />
<span class="small">The definition of 'URL.URL()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   The interface it belongs to: [`URL`](../url).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL/URL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL/URL</a>
