Window.localStorage
===================

The `localStorage` read-only property of the [`window`](../window) interface allows you to access a [`Storage`](../storage) object for the [`Document`](../document)'s [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin); the stored data is saved across browser sessions.

`localStorage` is similar to [`sessionStorage`](sessionstorage), except that while `localStorage` data has no expiration time, `sessionStorage` data gets cleared when the page session ends — that is, when the page is closed. (`localStorage` data for a document loaded in a "private browsing" or "incognito" session is cleared when the last "private" tab is closed.)

Syntax
------

    myStorage = window.localStorage;

### Value

A [`Storage`](../storage) object which can be used to access the current origin's local storage space.

### Exceptions

`SecurityError`  
The request violates a policy decision, or the origin is not [a valid scheme/host/port tuple](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy#definition_of_an_origin) (this can happen if the origin uses the `file:` or `data:` schemes, for example). For example, the user may have their browser configured to deny permission to persist data for the specified origin.

Description
-----------

The keys and the values stored with `localStorage` are *always* in the UTF-16 [`DOMString`](../domstring) format, which uses two bytes per character. As with objects, integer keys are automatically converted to strings.

`localStorage` data **is specific to the protocol of the document**. In particular, for a site loaded over HTTP (e.g., `http://example.com`), `localStorage` returns a different object than `localStorage` for the corresponding site loaded over HTTPS (e.g., `https://example.com`).

For documents loaded from `file:` URLs (that is, files opened in the browser directly from the user’s local filesystem, rather than being served from a web server) the requirements for `localStorage` behavior are undefined and may vary among different browsers.

In all current browsers, `localStorage` seems to return a different object for each `file:` URL. In other words, each `file:` URL seems to have its own unique local-storage area. But there are no guarantees about that behavior, so you shouldn’t rely on it because, as mentioned above, the requirements for `file:` URLs remains undefined. So it’s possible that browsers may change their `file:` URL handling for `localStorage` at any time. In fact some browsers *have* changed their handling for it over time.

Example
-------

The following snippet accesses the current domain's local [`Storage`](../storage) object and adds a data item to it using [`Storage.setItem()`](../storage/setitem).

    localStorage.setItem('myCat', 'Tom');

The syntax for reading the `localStorage` item is as follows:

    const cat = localStorage.getItem('myCat');

The syntax for removing the `localStorage` item is as follows:

    localStorage.removeItem('myCat');

The syntax for removing all the `localStorage` items is as follows:

    localStorage.clear();

**Note**: Please refer to the [Using the Web Storage API](../web_storage_api/using_the_web_storage_api) article for a full example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webstorage.html#dom-localstorage">HTML Living Standard<br />
<span class="small">The definition of 'localStorage' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`localStorage`

4

12

3.5

8

10.5

4

≤37

18

4

11

3.2

1.0

See also
--------

-   [Using the Web Storage API](../web_storage_api/using_the_web_storage_api)
-   [`Window.sessionStorage`](sessionstorage)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage</a>
