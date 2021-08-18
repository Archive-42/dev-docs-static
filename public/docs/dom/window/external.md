Window.external
===============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `external` property of the [`Window`](../window) API returns an instance of the `External` interface, which was intended to contain functions related to adding external search providers to the browser. However, this is now deprecated, and the contained methods are now dummy functions that do nothing as per spec.

Methods
-------

The `External` object has the following methods:

<table><thead><tr class="header"><th>Method</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>AddSearchProvider(descriptionURL)</code></td><td>Dummy function; does nothing. See <a href="https://developer.mozilla.org/en-US/docs/Web/OpenSearch#autodiscovery_of_search_plugins">Autodiscovery of search plugins</a>.</td></tr><tr class="even"><td><code>IsSearchProviderInstalled()</code></td><td>Dummy function; does nothing.</td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#external">HTML Living Standard<br />
<span class="small">The definition of 'External' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`external`

Yes

12

2

From Firefox 78 `AddSearchProvider()` does nothing, as the specification requires.

4

15

No

Yes

Yes

4

From Firefox for Android 79 `AddSearchProvider()` does nothing, as the specification requires.

14

No

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/external" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/external</a>
