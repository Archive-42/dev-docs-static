Storage Access API
==================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The Storage Access API provides a way for embedded, cross-origin content to gain unrestricted access to storage that it would normally only have access to in a first-party context (we refer to this as an origin’s *first-party* storage). The API provides methods that allow embedded resources to check whether they currently have access to their first-party storage, and to request access to their first-party storage from the user agent.

Concepts and usage
------------------

Most browsers implement a number of storage access policies that restrict access to cookies and site data for embedded, cross-origin resources. These restrictions range from giving embedded resources under each top-level origin a unique storage space to outright blocking of storage access when resources are loaded in a third-party context.

The semantics around third-party cookie blocking policies in particular differ from browser to browser, but the core functionality is similar: cross-origin resources embedded in a third-party context are not given access to the same cookies and site storage that they would have access to when loaded in a first-party context.

These cookie blocking policies are known to break embedded cross-origin content that requires access to its first-party storage. As an example, federated logins often require access to authentication cookies stored in first-party storage, and will require the user to sign in on each site separately (or completely break) if those cookies are not available. In the case of breakage, site owners have often encouraged users to add their site as an exception or to disable the policy entirely. As a consequence, users who wish to continue to interact with embedded content are forced to greatly relax their blocking policy for resources loaded from all embedded origins and possibly across all websites.

The Storage Access API is intended to solve this problem; embedded cross-origin content can request unrestricted access to its first-party storage on a site-by-site basis via the [`Document.requestStorageAccess()`](document/requeststorageaccess) method, and check whether it already has access via the [`Document.hasStorageAccess()`](document/hasstorageaccess) method.

In addition, sandboxed [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)s cannot be granted storage access by default for security reasons. The API therefore also adds the `allow-storage-access-by-user-activation` [sandbox token](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-sandbox). The embedding website needs to add this to allow storage access requests to be successful, along with `allow-scripts` and `allow-same-origin` to allow it to call the API, and execute in an origin that can have cookies:

    <iframe sandbox="allow-storage-access-by-user-activation
                     allow-scripts
                     allow-same-origin">
      ...
    </iframe>

The API is designed to limit the potential storage exceptions to origins for which the user has shown an intent to interact. This is enforced through the following constraints:

-   Access requests are automatically denied unless the embedded content is currently processing a user gesture such as a tap or click. This also prevents embedded content on the page from spamming the browser or user with excessive access requests.
-   Origins that have never been interacted with as a first party do not have a notion of first-party storage. From the user’s perspective, they only have a third-party relationship with that origin. Access requests are automatically denied if the browser detects that the user hasn’t interacted with the embedded content in a first-party context recently (in Firefox, "recently" is "within 30 days").

The browser may decide to involve the user in the decision of whether to grant an incoming storage access request. Specifics regarding the lifetime of a storage grant and the circumstances under which the browser may decide to inform the user are currently being worked through and will be announced once ready.

User prompts
------------

When `requestStorageAccess()` is called by an embedded, cross-origin document, the user agent may choose to involve the user in the decision of whether to grant storage access to the requesting origin. Prompting heuristics currently vary across the two implementers of the Storage Access API — Safari shows prompts for all embedded tracking content that has not previously received storage access, while Firefox only prompts users after a tracking origin has requested storage access on more than a threshold number of sites. See [`Document.requestStorageAccess()`](document/requeststorageaccess) for more details.

Safari implementation differences
---------------------------------

Although the API surface is the same, websites using the Storage Access API should expect differences in the level and extent of storage access they receive between Firefox and Safari. This is caused by differences in the storage access policies implemented in the two browsers. Design properties unique to Firefox are summarized here:

-   If the embedded origin `tracker.example` has already obtained first-party storage access on the top-level origin `foo.example`, and the user visits a page from `foo.example` embedding a page from `tracker.example` again in less than 30 days, the embedded origin will have storage access immediately when loading.
-   If a page from top-level origin `foo.example` embeds more than one [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) from `tracker.example`, and one of those `<iframe>`s uses the Storage Access API in order to obtain storage access successfully, all other iframes from `tracker.example` on `foo.example` top-level origins will immediately gain storage access as well, without needing to call `requestStorageAccess()` separately.
-   If an embedded page from `tracker.example` has previously successfully obtained storage access on top-level origin `foo.example`, all embedded subresources from `tracker.example` on `foo.example` (e.g. scripts, images, stylesheets, etc.) will load with access to their first-party storage, which means they may send Cookie headers and honor incoming [`Set-Cookie`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie) headers.
-   In Firefox, when the promise returned from `requestStorageAccess()` is resolved, the embedded page will gain access to its entire first-party storage, not just cookies. This includes access to APIs such as [Web Storage](web_storage_api), [IndexedDB](indexeddb_api), [DOM Cache](cache), and so on.
-   In Firefox, the storage access grants are phased out after 30 calendar days passing, whereas in Safari the storage access grants are phased out after 30 days of browser usage passed without user interaction. This is currently a limitation of the Firefox implementation, which we may address in a future version. In Safari, successful use of the storage access API resets this counter.

Documentation for Firefox's new storage access policy for blocking tracking cookies includes [a detailed description](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Privacy/Storage_access_policy#storage_access_grants) of the scope of storage access grants.

Storage Access API methods
--------------------------

The storage API methods are implemented on the [`Document`](document) interface:

[`Document.hasStorageAccess()`](document/hasstorageaccess)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a boolean value indicating whether the document has access to its first-party storage.

[`Document.requestStorageAccess()`](document/requeststorageaccess)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves if the access to first-party storage was granted, and rejects if access was denied.

**Note**: User interaction propagates to the Promise returned by both of these methods, allowing the callers to take actions that require user interaction without requiring a second click from the user. For example, a caller could open a pop-up window from the resolved Promise without triggering Firefox’s pop-up blocker.

Extensions to &lt;iframe&gt; sandbox
------------------------------------

The [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) element's `sandbox` attribute has a new token, `allow-storage-access-by-user-activation`, which permits sandboxed `<iframe>`s to use the Storage Access API to request storage access.

Specifications
--------------

The API is currently only at the proposal stage — the standardization process has yet to begin. You can currently find specification details of the API at Apple's [Introducing Storage Access API](https://webkit.org/blog/8124/introducing-storage-access-api/) blog post, and [WHATWG HTML issue 3338 — Proposal: Storage Access API](https://github.com/whatwg/html/issues/3338).

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

`Storage_Access_API`

78

85

65

No

65

11.1

No

78

65

No

11.3

No

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

`Storage_Access_API`

78

85

65

No

65

11.1

No

78

65

No

11.3

No

BCD tables only load in the browser

BCD tables only load in the browser

See also
--------

[Using the Storage Access API](storage_access_api/using)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Storage_Access_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Storage_Access_API</a>
