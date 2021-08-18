Window.sidebar
==============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Returns a sidebar object which contains several methods for registering add-ons with the browser.

Methods
-------

The sidebar object returned has the following methods:

Method

Description (SeaMonkey)

Description (Firefox)

`addPanel(title, contentURL, "")`

Adds a sidebar panel.

Obsolete since Firefox 23 (only present in SeaMonkey).  
End users can use the "load this bookmark in the sidebar" option instead. Also see [Creating a Firefox sidebar.](https://developer.mozilla.org/en-US/docs/Mozilla/Creating_a_Firefox_sidebar)

`addPersistentPanel(title, contentURL, "")`

Adds a sidebar panel, which is able to work in the background.

`AddSearchProvider(descriptionURL)`

Dummy function; does nothing. See [Autodiscovery of search plugins](https://developer.mozilla.org/en-US/docs/Web/OpenSearch#autodiscovery_of_search_plugins).

`addSearchEngine(engineURL, iconURL, suggestedTitle, suggestedCategory)` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>

Installs a search engine (Sherlock). [Adding Sherlock search engines](https://developer.mozilla.org/en-US/docs/Web/OpenSearch#installing_sherlock_plugins) contains more details.

**Note**: This was made obsolete in Firefox 44, and has been removed completely in Firefox 59.

`IsSearchProviderInstalled(descriptionURL)`

Indicates if a specific search provider (OpenSearch) is installed.

Specifications
--------------

Mozilla-specific. Not part of any standard.

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

`sidebar`

No

No

1

From Firefox 78 `AddSearchProvider()` does nothing, as the specification requires.

No

?

No

No

No

4

?

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/sidebar" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/sidebar</a>
