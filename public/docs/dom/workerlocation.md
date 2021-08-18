WorkerLocation
==============

The `WorkerLocation` interface defines the absolute location of the script executed by the [`Worker`](worker). Such an object is initialized for each worker and is available via the [`WorkerGlobalScope.location`](workerglobalscope/location) property obtained by calling `self.location`.

This interface is only visible from inside a JavaScript script executed in the context of a Web worker.

Properties
----------

*The `WorkerLocation` interface doesn't inherit any property, but implements properties defined in the [`URLUtilsReadOnly`](urlutilsreadonly) interface.*

 [`URLUtilsReadOnly.href`](urlutilsreadonly/href) <span class="badge inline readonly">Read only </span>   
Is a stringifier that returns a [`DOMString`](domstring) containing the whole URL of the script executed in the [`Worker`](worker).

 [`URLUtilsReadOnly.protocol`](urlutilsreadonly/protocol) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing the protocol scheme of the URL of the script executed in the [`Worker`](worker), including the final `':'`.

 [`URLUtilsReadOnly.host`](urlutilsreadonly/host) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing the host, that is the *hostname*, a `':'`, and the *port* of the URL of the script executed in the [`Worker`](worker).

 [`URLUtilsReadOnly.hostname`](urlutilsreadonly/hostname) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing the domain of the URL of the script executed in the [`Worker`](worker).

 [`URLUtilsReadOnly.origin`](urlutilsreadonly/origin) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) containing the canonical form of the origin of the specific location.

 [`URLUtilsReadOnly.port`](urlutilsreadonly/port) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing the port number of the URL of the script executed in the [`Worker`](worker).

 [`URLUtilsReadOnly.pathname`](urlutilsreadonly/pathname) <span class="badge inline readonly">Read only </span>   
Is a [`USVString`](usvstring) containing an initial `'/'` followed by the path of the URL (not including the query string or fragment) of the script executed in the [`Worker`](worker).

 [`URLUtilsReadOnly.search`](urlutilsreadonly/search) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing a `'?'` followed by the parameters of the URL of the script executed in the [`Worker`](worker).

 [`URLUtilsReadOnly.hash`](urlutilsreadonly/hash) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing a `'#'` followed by the fragment identifier of the URL of the script executed in the [`Worker`](worker).

Methods
-------

*The `WorkerLocation` interface doesn't inherit any method, but implements methods defined in the [`URLUtilsReadOnly`](urlutilsreadonly) interface.*

[`URLUtilsReadOnly.toString()`](urlutilsreadonly/tostring)  
Returns a [`DOMString`](domstring) containing the whole URL of the script executed in the [`Worker`](worker). It is a synonym for [`URLUtilsReadOnly.href`](urlutilsreadonly/href).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#workerlocation">HTML Living Standard<br />
<span class="small">The definition of 'WorkerLocation' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`WorkerLocation`

1

≤79

3.5

?

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

See also
--------

-   Other Worker-related interfaces: [`Worker`](worker), [`WorkerNavigator`](workernavigator), and [`WorkerGlobalScope`](workerglobalscope).
-   [Using web workers](web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation</a>
