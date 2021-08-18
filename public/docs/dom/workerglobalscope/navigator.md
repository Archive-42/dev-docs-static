WorkerGlobalScope.navigator
===========================

The `navigator` read-only property of the [`WorkerGlobalScope`](../workerglobalscope) interface returns the [`WorkerNavigator`](../workernavigator) associated with the worker. It is a specific navigator object, mostly a subset of the [`Navigator`](../navigator) for browsing scopes, but adapted to workers.

Syntax
------

    var navigatorObj = self.navigator;

### Value

A [`WorkerNavigator`](../workernavigator) object.

Example
-------

If you call the following

    console.log(navigator);

inside a worker (which would basically be the equivalent of `self.console.log(self.navigator);`, as these are being called on the worker scope, which can be referenced with [`WorkerGlobalScope.self`](self)), you will get a [`WorkerNavigator`](../workernavigator) object written to the console — something like the following:

    Object {onLine: true, userAgent: "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_1) Ap…ML, like Gecko) Chrome/40.0.2214.93 Safari/537.36", product: "Gecko", platform: "MacIntel", appVersion: "5.0 (Macintosh; Intel Mac OS X 10_10_1) AppleWebKi…ML, like Gecko) Chrome/40.0.2214.93 Safari/537.36"…}
        appCodeName: "Mozilla"
        appName: "Netscape"
        appVersion: "5.0 (Macintosh; Intel Mac OS X 10_10_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/40.0.2214.93 Safari/537.36"
        hardwareConcurrency: 4
        onLine: true
        platform: "MacIntel"
        product: "Gecko"
        userAgent: "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/40.0.2214.93 Safari/537.36"
        __proto__: Object

You could use this navigator object to return more information about the runtime envinronment, as you might do with a normal [`Navigator`](../navigator) object.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-worker-navigator">HTML Living Standard<br />
<span class="small">The definition of 'navigator' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`navigator`

4

17

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

[`WorkerNavigator`](../workernavigator)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/navigator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/navigator</a>
