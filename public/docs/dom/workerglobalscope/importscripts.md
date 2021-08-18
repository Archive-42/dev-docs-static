WorkerGlobalScope.importScripts()
=================================

The `importScripts()` method of the [`WorkerGlobalScope`](../workerglobalscope) interface synchronously imports one or more scripts into the worker's scope.

Syntax
------

    self.importScripts('foo.js');
    self.importScripts('foo.js', 'bar.js', ...);

### Parameters

A comma-separated list of [`DOMString`](../domstring) objects representing the scripts to be imported. These paths are relative to *html document base URL*.

### Return value

*None.*

### Exceptions

`NetworkError`  
Imported scripts were not served with a valid JavaScript MIME type (i.e. `text/javascript`).

Example
-------

If you had some functionality written in a separate script called `foo.js` that you wanted to use inside worker.js, you could import it using the following line:

    importScripts('foo.js');

`importScripts()` and `self.importScripts()` are effectively equivalent — both represent `importScripts()` being called from inside the worker's inner scope.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-workerglobalscope-importscripts">HTML Living Standard<br />
<span class="small">The definition of 'importScripts()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`importScripts`

4

12

4

10

10.6

4

≤37

18

4

11

3.2

1.0

`mime_checks`

71

≤79

67

?

58

No

71

71

67

50

No

10.0

See also
--------

-   [`WorkerGlobalScope`](../workerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/importScripts" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/importScripts</a>
