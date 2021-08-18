Location: reload()
==================

The `Location.reload()` method reloads the current URL, like the Refresh button.

The reload may be blocked and a `SECURITY_ERROR` [`DOMException`](../domexception) thrown. This happens if the [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin) of the script calling `location.reload()` differs from the origin of the page that owns the [`Location`](../location) object. See [Same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy) for more information.

Syntax
------

    location.reload();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/history.html#dom-location-reload">HTML Living Standard<br />
<span class="small">The definition of 'Location.reload()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-location-reload">HTML5<br />
<span class="small">The definition of 'Location.reload()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`reload`

1

12

Before Edge 79, if a page added to *Trusted Sites* contains a cross-origin iframe, then calling `reload()` from within the iframe reloads the trusted page (in other words, the top page reloads, not the iframe).

1

5.5

If a page added to *Trusted Sites* contains a cross-origin iframe, then calling `reload()` from within the iframe reloads the trusted page (in other words, the top page reloads, not the iframe).

3

1

1

18

4

10.1

1

1.0

See also
--------

-   The [`Location`](../location) interface it belongs to.
-   Similar methods: [`Location.assign()`](assign) and [`Location.replace()`](replace).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/reload" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/reload</a>
