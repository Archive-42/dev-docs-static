URL.href
========

The `href` property of the [`URL`](../url) interface is a [`USVString`](../usvstring) containing the whole URL.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    const urlString = url.href
    url.href = newUrlString

### Value

A [`USVString`](../usvstring).

Examples
--------

    const url = new URL('https://developer.mozilla.org/en-US/docs/Web/API/URL/href');
    console.log(url.href); // Logs: 'https://developer.mozilla.org/en-US/docs/Web/API/URL/href'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-url-href">URL<br />
<span class="small">The definition of 'URL.href' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   The [`URL`](../url) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL/href" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL/href</a>
