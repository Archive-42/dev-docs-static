URLUtilsReadOnly
================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The **obsolete** `URLUtilsReadOnly` interface previously defined utility methods for working with URLs. These were then inherited by other interfaces, such as [`WorkerLocation`](workerlocation). `URLUtilsReadOnly` has been removed from the specification, and the properties it defined are now directly part of the affected interfaces.

Properties
----------

*This interface doesn't inherit any properties.*

 [`URLUtilsReadOnly.href`](urlutilsreadonly/href) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing the whole URL.

 [`URLUtilsReadOnly.protocol`](urlutilsreadonly/protocol) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing the protocol scheme of the URL, including the final `':'`.

 [`URLUtilsReadOnly.host`](urlutilsreadonly/host) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing the host, that is the *hostname*, a `':'`, and the *port* of the URL.

 [`URLUtilsReadOnly.hostname`](urlutilsreadonly/hostname) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing the domain of the URL.

 [`URLUtilsReadOnly.origin`](urlutilsreadonly/origin) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) containing the canonical form of the origin of the specific location.

 [`URLUtilsReadOnly.port`](urlutilsreadonly/port) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing the port number of the URL.

 [`URLUtilsReadOnly.pathname`](urlutilsreadonly/pathname) <span class="badge inline readonly">Read only </span>   
Is a [`USVString`](usvstring) containing an initial `'/'` followed by the path of the URL, not including the query string or fragment.

 [`URLUtilsReadOnly.search`](urlutilsreadonly/search) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing a `'?'` followed by the parameters of the URL.

 [`URLUtilsReadOnly.hash`](urlutilsreadonly/hash) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing a `'#'` followed by the fragment identifier of the URL.

Methods
-------

*This interface doesn't inherit any methods.*

[`URLUtilsReadOnly.toString()`](urlutilsreadonly/tostring)  
Returns a [`DOMString`](domstring) containing the whole URL. It is a synonym for [`URLUtilsReadOnly.href`](urlutilsreadonly/href).

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

`URLUtilsReadOnly`

No

No

57

3.5-57

Firefox has a bug whereby single quotes contained in URLs are escaped when accessed via URL APIs (see [bug 1386683](https://bugzil.la/1386683)).

No

No

No

No

No

57

4-57

Firefox has a bug whereby single quotes contained in URLs are escaped when accessed via URL APIs (see [bug 1386683](https://bugzil.la/1386683)).

No

No

No

`hash`

No

No

38

3.5-38

Before Firefox 38, Firefox returned the hash percent encoded. This has been fixed to match the spec.

No

No

No

No

No

38

4-38

Before Firefox 38, Firefox returned the hash percent encoded. This has been fixed to match the spec.

No

No

No

`host`

No

No

3.5

No

No

No

No

No

4

No

No

No

`hostname`

No

No

3.5

No

No

No

No

No

4

No

No

No

`href`

No

No

3.5

No

No

No

No

No

4

No

No

No

`origin`

No

No

29

No

No

No

No

No

29

No

No

No

`pathname`

No

No

3.5

No

No

No

No

No

4

No

No

No

`port`

No

No

3.5

No

No

No

No

No

4

No

No

No

`protocol`

No

No

3.5

No

No

No

No

No

4

No

No

No

`search`

No

No

3.5

No

No

No

No

No

4

No

No

No

`toString`

No

No

3.5

No

No

No

No

No

4

No

No

No

See also
--------

-   Other URL-related interfaces: [`URL`](url), <span class="page-not-created">`URLUtils`</span>, and <span class="page-not-created">`URLQuery`</span>.
-   Interfaces implementing this one: [`WorkerLocation`](workerlocation).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly</a>
