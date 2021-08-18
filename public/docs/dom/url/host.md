URL.host
========

The `host` property of the [`URL`](../url) interface is a [`USVString`](../usvstring) containing the host, that is the [`hostname`](hostname), and then, if the [port](https://developer.mozilla.org/en-US/docs/Glossary/Port) of the URL is nonempty, a `':'`, followed by the [`port`](port) of the URL.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    const host = url.host
    url.host = newHost

### Value

A [`USVString`](../usvstring).

Examples
--------

    let url = new URL('https://developer.mozilla.org/en-US/docs/Web/API/URL/host');
    console.log(url.host); // "developer.mozilla.org"

    url = new URL('https://developer.mozilla.org:443/en-US/docs/Web/API/URL/host');
    console.log(url.host); // "developer.mozilla.org"
    // The port number is not included because 443 is the scheme's default port

    url = new URL('https://developer.mozilla.org:4097/en-US/docs/Web/API/URL/host');
    console.log(url.host); // "developer.mozilla.org:4097"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-url-host">URL<br />
<span class="small">The definition of 'URL.host' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   The [`URL`](../url) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL/host" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL/host</a>
