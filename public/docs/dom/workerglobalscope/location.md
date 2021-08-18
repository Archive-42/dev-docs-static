WorkerGlobalScope.location
==========================

The `location` read-only property of the [`WorkerGlobalScope`](../workerglobalscope) interface returns the [`WorkerLocation`](../workerlocation) associated with the worker. It is a specific location object, mostly a subset of the [`Location`](../location) for browsing scopes, but adapted to workers.

Syntax
------

    var locationObj = self.location;

### Value

A [`WorkerLocation`](../workerlocation) object.

Example
-------

If you called the following in a document served at `localhost:8000`

    console.log(location);

inside a worker (which would basically be the equivalent of `self.console.log(self.location);`, as these are being called on the worker scope, which can be referenced with [`WorkerGlobalScope.self`](self)), you will get a [`WorkerLocation`](../workerlocation) object written to the console — something like the following:

    WorkerLocation {hash: "", search: "", pathname: "/worker.js", port: "8000", hostname: "localhost"…}
      hash: ""
      host: "localhost:8000"
      hostname: "localhost"
      href: "http://localhost:8000/worker.js"
      origin: "http://localhost:8000"
      pathname: "/worker.js"
      port: "8000"
      protocol: "http:"
      search: ""
      __proto__: WorkerLocation

You could use this location object to return more information about the document's location, as you might do with a normal [`Location`](../location) object.

**Note**: Firefox has a bug with using `console.log` inside shared/service workers (see [bug 1058644](https://bugzilla.mozilla.org/show_bug.cgi?id=1058644)), which may return strange results, but this should be fixed soon.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-workerglobalscope-location">HTML Living Standard<br />
<span class="small">The definition of 'location' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`location`

4

12

3.5

Yes

11.5

4

37

40

4

Yes

5.1

4.0

See also
--------

[`WorkerGlobalScope`](../workerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/location" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/location</a>
