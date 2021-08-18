URL.origin
==========

The `origin` read-only property of the [`URL`](../url) interface returns a [`USVString`](../usvstring) containing the Unicode serialization of the origin of the represented URL. The exact structure varies depending on the type of URL:

-   For `http` or `https` URLs, the scheme followed by `'://'`, followed by the domain, followed by `':'`, followed by the port (the default port, `80` and `443` respectively, if explicitly specified).
-   For `file:` URLs, the value is browser dependant.
-   for `blob:` URLs, the origin of the URL following `blob:` will be used, e.g `"blob:https://mozilla.org"` will be returned as `"https://mozilla.org".`

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    const originString = url.origin

### Value

A [`USVString`](../usvstring).

Examples
--------

    const url = new URL("blob:https://mozilla.org:443/")
    console.log(url.origin); // Logs 'https://mozilla.org'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-url-origin">URL<br />
<span class="small">The definition of 'URL.origin' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   The [`URL`](../url) interface

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL/origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL/origin</a>
