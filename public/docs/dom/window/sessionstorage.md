Window.sessionStorage
=====================

The read-only `sessionStorage` property accesses a session [`Storage`](../storage) object for the current [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin). `sessionStorage` is similar to [`localStorage`](localstorage); the difference is that while data in `localStorage` doesn't expire, data in `sessionStorage` is cleared when the *page session* ends.

-   Whenever a document is loaded in a particular tab in the browser, a unique page session gets created and assigned to that particular tab. That page session is valid only for that particular tab.
-   A page session lasts as long as the tab or the browser is open, and survives over page reloads and restores.
-   **Opening a page in a new tab or window creates a new session with the value of the top-level browsing context, which differs from how session cookies work.**
-   Opening multiple tabs/windows with the same URL creates `sessionStorage` for each tab/window.
-   Duplicating a tab copies the tab's `sessionStorage` into the new tab.
-   Closing a tab/window ends the session and clears objects in `sessionStorage`.

Data stored in `sessionStorage` **is specific to the protocol of the page**. In particular, data stored by a script on a site accessed with HTTP (e.g., [http://example.com](https://example.com)) is put in a different `sessionStorage` object from the same site accessed with HTTPS (e.g., <https://example.com>).

The keys and the values are *always* in the UTF-16 [`DOMString`](../domstring) format, which uses two bytes per character. As with objects, integer keys are automatically converted to strings.

Syntax
------

    myStorage = window.sessionStorage;

### Value

A [`Storage`](../storage) object which can be used to access the current origin's session storage space.

### Exceptions

`SecurityError`  
The request violates a policy decision, or the origin is not [a valid scheme/host/port tuple](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy#definition_of_an_origin) (this can happen if the origin uses the `file:` or `data:` scheme, for example). For example, the user may have their browser configured to deny permission to persist data for the specified origin.

Examples
--------

### Basic usage

    // Save data to sessionStorage
    sessionStorage.setItem('key', 'value');

    // Get saved data from sessionStorage
    let data = sessionStorage.getItem('key');

    // Remove saved data from sessionStorage
    sessionStorage.removeItem('key');

    // Remove all saved data from sessionStorage
    sessionStorage.clear();

### Saving text between refreshes

The following example autosaves the contents of a text field, and if the browser is refreshed, restores the text field content so that no writing is lost.

    // Get the text field that we're going to track
    let field = document.getElementById("field");

    // See if we have an autosave value
    // (this will only happen if the page is accidentally refreshed)
    if (sessionStorage.getItem("autosave")) {
      // Restore the contents of the text field
      field.value = sessionStorage.getItem("autosave");
    }

    // Listen for changes in the text field
    field.addEventListener("change", function() {
      // And save the results into the session storage object
      sessionStorage.setItem("autosave", field.value);
    });

**Note**: Please refer to the [Using the Web Storage API](../web_storage_api/using_the_web_storage_api) article for a full example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webstorage.html#dom-sessionstorage">HTML Living Standard<br />
<span class="small">The definition of 'sessionStorage' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`sessionStorage`

5

12

2

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
-   [`Window.localStorage`](localstorage)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage</a>
