URL.hash
========

The `hash` property of the [`URL`](../url) interface is a [`USVString`](../usvstring) containing a `'#'` followed by the fragment identifier of the URL.

The fragment is not [percent-decoded](https://developer.mozilla.org/en-US/docs/Glossary/percent-encoding). If the URL does not have a fragment identifier, this property contains an empty string — `""`.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    const string = url.hash
    url.hash = newHash

### Value

A [`USVString`](../usvstring).

Examples
--------

    const url = new URL('https://developer.mozilla.org/en-US/docs/Web/API/URL/href#Examples');
    console.log(url.hash); // Logs: '#Examples'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-url-hash">URL<br />
<span class="small">The definition of 'URL.hash' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   The [`URL`](../url) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL/hash" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL/hash</a>
