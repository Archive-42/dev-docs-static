Clear-Site-Data
===============

The `Clear-Site-Data` header clears browsing data (cookies, storage, cache) associated with the requesting website. It allows web developers to have more control over the data stored locally by a browser for their origins.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

The `Clear-Site-Data` header accepts one or more directives. If all types of data should be cleared, the wildcard directive (`"*"`) can be used.

    // Single directive
    Clear-Site-Data: "cache"

    // Multiple directives (comma separated)
    Clear-Site-Data: "cache", "cookies"

    // Wild card
    Clear-Site-Data: "*"

Directives
----------

All directives must comply with the [quoted-string grammar](https://tools.ietf.org/html/rfc7230#section-3.2.6). A directive that does not include the double quotes is invalid.

`"cache"`  
Indicates that the server wishes to remove locally cached data (i.e. the browser cache, see [HTTP caching](../caching)) for the origin of the response URL. Depending on the browser, this might also clear out things like pre-rendered pages, script caches, WebGL shader caches, or address bar suggestions.

`"cookies"`  
Indicates that the server wishes to remove all cookies for the origin of the response URL. HTTP authentication credentials are also cleared out. This affects the entire registered domain, including subdomains. So https://example.com as well as https://stage.example.com, will have cookies cleared.

`"storage"`  
Indicates that the server wishes to remove all DOM storage for the origin of the response URL. This includes storage mechanisms such as:

-   localStorage (executes `localStorage.clear`),
-   sessionStorage (executes `sessionStorage.clear`),
-   IndexedDB (for each database execute [`IDBFactory.deleteDatabase`](https://developer.mozilla.org/en-US/docs/Web/API/IDBFactory/deleteDatabase)),
-   Service worker registrations (for each service worker registration, execute [`ServiceWorkerRegistration.unregister`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/unregister)),
-   [AppCache,](https://developer.mozilla.org/en-US/docs/Web/HTML/Using_the_application_cache)
-   WebSQL databases,
-   [FileSystem API data](https://developer.mozilla.org/en-US/docs/Web/API/File_and_Directory_Entries_API),
-   Plugin data (Flash via `NPP_ClearSiteData`).

`"executionContexts"`  
Indicates that the server wishes to reload all browsing contexts for the origin of the response ([`Location.reload`](https://developer.mozilla.org/en-US/docs/Web/API/Location/reload)).

 `"*"` (wildcard)  
Indicates that the server wishes to clear all types of data for the origin of the response. If more data types are added in future versions of this header, they will also be covered by it.

Examples
--------

### Sign out of web site

If a user signs out of your website or service, you might want to remove locally stored data. You can achieve that by adding the `Clear-Site-Data` header when sending the page confirming that logging out from the site has been accomplished successfully (https://example.com/logout, for example):

    Clear-Site-Data: "cache", "cookies", "storage", "executionContexts"

### Clearing cookies

If this header is delivered with the response at https://example.com/clear-cookies, all cookies on the same domain https://example.com and any subdomains (like https://stage.example.com, etc), will be cleared out.

    Clear-Site-Data: "cookies"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-clear-site-data">Clear Site Data</a></td><td>Working Draft</td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Clear-Site-Data`

61

≤79

63

63

62

Disabled

Disabled From version 62: this feature is behind the `dom.clearSiteData.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

?

48

?

[`"cache"`](#cache)

61

≤79

63

63

62

Disabled

Disabled From version 62: this feature is behind the `dom.clearSiteData.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

?

48

?

[`"cookies"`](#cookies)

61

≤79

63

63

62

Disabled

Disabled From version 62: this feature is behind the `dom.clearSiteData.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

?

48

?

[`"executionContexts"`](#executionContexts)

No

 No   
See [bug 898503](https://crbug.com/898503).

No

 No   
See [bug 898503](https://crbug.com/898503).

63 — 68

63 — 68

62

Disabled

Disabled From version 62: this feature is behind the `dom.clearSiteData.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

?

No

?

[`"storage"`](#storage)

61

≤79

63

63

62

Disabled

Disabled From version 62: this feature is behind the `dom.clearSiteData.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

?

48

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Clear-Site-Data`

61

61

63

63

62

Disabled

Disabled From version 62: this feature is behind the `dom.clearSiteData.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

45

?

8.0

[`"cache"`](#cache)

61

61

63

63

62

Disabled

Disabled From version 62: this feature is behind the `dom.clearSiteData.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

45

?

8.0

[`"cookies"`](#cookies)

61

61

63

63

62

Disabled

Disabled From version 62: this feature is behind the `dom.clearSiteData.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

45

?

8.0

[`"executionContexts"`](#executionContexts)

No

No

63 — 68

63 — 68

62

Disabled

Disabled From version 62: this feature is behind the `dom.clearSiteData.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

?

8.0

[`"storage"`](#storage)

61

61

63

63

62

Disabled

Disabled From version 62: this feature is behind the `dom.clearSiteData.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

45

?

8.0

See also
--------

-   [`Cache-Control`](cache-control)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Clear-Site-Data$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Clear-Site-Data" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Clear-Site-Data</a>
